**Docker Single-Stage vs Multi-Stage Builds
**

Overview

Docker images can be built using:
---------------------------------
Single-Stage Build
Multi-Stage Build

Multi-stage builds are mainly used to:

reduce image size
improve security
create production-ready containers



<img width="1043" height="362" alt="image" src="https://github.com/user-attachments/assets/0680b1d1-72ac-4150-bd1b-2fa050ffc3fa" />


<img width="1012" height="457" alt="image" src="https://github.com/user-attachments/assets/8b9684aa-5050-4147-b158-133c747c31e7" />

---------------------------------------------------------------------------------------------------------------------------------------------

**Single-Stage Build
**

In a single-stage build, everything remains inside one image:

build tools
compilers
dependencies
application code
-------------------------------------------------------------------------------------------------------------------------------------------------
Example :
FROM python:3.11

WORKDIR /app

RUN apt-get update && apt-get install -y \
    build-essential \
    gcc \
    curl

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["python", "app.py"]

------------------------------------------------------------------------------------------------------------------------------------
**Problems with Single-Stage Builds
**
The final image still contains:

gcc
build-essential
apt cache
temporary files

This results in:

larger image size
more vulnerabilities
slower deployments

**Multi-Stage Build
**
Multi-stage builds separate:

build environment
runtime environment

Only required runtime files are copied into the final image.
Example: 
# ---------- Builder Stage ----------
FROM python:3.11 AS builder

WORKDIR /app

RUN apt-get update && apt-get install -y \
    build-essential \
    gcc \
    curl

COPY requirements.txt .

RUN pip install --no-cache-dir --prefix=/install -r requirements.txt

COPY . .

# ---------- Runtime Stage ----------
FROM python:3.11-slim

WORKDIR /app

COPY --from=builder /install /usr/local

COPY app.py .

CMD ["python", "app.py"]
------------------------------------------------------------------------------------------------------------------------------------

**Key Concept
**COPY --from=builder /install /usr/local
This copies only required runtime dependencies from the builder stage into the final image.

**Why Install gcc and build-essential?
**
Some Python packages require compilation during installation.

Examples:

numpy
pandas
cryptography

Build tools are needed only during build time, not during runtime



**Build Flow
**

Single-Stage
Install Build Tools
→ Install Dependencies
→ Run Application

Everything stays inside the image.

**Multi-Stage**
Builder Stage
→ Install Build Tools
→ Build Application

Runtime Stage
→ Copy Required Files Only
→ Run Application


**Advantages of Multi-Stage Builds
**
Smaller image size
Better security
Faster deployments
Cleaner production images

Build Commands
Build Single-Stage Image

docker build -f Dockerfile.single -t flask-single .

Build Multi-Stage Image
docker build -f Dockerfile.multi-stage -t flask-multi .

------------------------------------------------------------------------------------------------------------------------------------



