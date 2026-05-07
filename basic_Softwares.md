**What is Flask?
**
Flask is a lightweight Python web framework used to create:

Flask App → Docker → Kubernetes

**What is Django?
**
Django is a full-featured Python web framework.


**Difference Between Flask and Django
**
Flask	Django
Minimal	Full-featured
Lightweight	Heavy
Flexible	Structured
Good for APIs	Good for large web apps
Faster to start small	Faster for enterprise apps



Real-World Example
Flask
Small API service.
Django
Full e-commerce website.



React Runs in Browser
Unlike Flask/Django:
	• React is frontend 
	• runs in browser 
	• talks to backend APIs

Architecture Example
React Frontend
      ↓ API Calls
Flask/Django Backend
      ↓
Database

**What is Distroless?
**
Distroless images are ultra-minimal container images.

They contain:
	• ONLY runtime dependencies 
	• NO package managers 
	• NO shell 
	• NO Linux utilities

Normal Image:
Ubuntu
bash
apt
curl
gcc
python
app

**Distroless Image
**python runtime
application only

<img width="1007" height="551" alt="image" src="https://github.com/user-attachments/assets/903db405-fe20-4cf0-b89f-eb1798859ac4" />

<img width="601" height="348" alt="image" src="https://github.com/user-attachments/assets/b65d8047-ec42-4de5-9c09-6def5458791e" />



**Typical DevOps Flow
**
Developer writes Flask API
        ↓
Dockerfile created
        ↓
React frontend built
        ↓
Multi-stage Docker build
        ↓
Pushed to registry
        ↓
Deployed to Kubernetes

