What is Flask?
Flask is a lightweight Python web framework used to create:
Flask App → Docker → Kubernetes

What is Django?
Django is a full-featured Python web framework.


Difference Between Flask and Django
Flask	Django
Minimal	Full-featured
Lightweight	Heavy
Flexible	Structured
Good for APIs	Good for large web apps
Faster to start small	Faster for enterprise apps

From <https://chatgpt.com/c/69fbf514-3210-8321-8dd5-f98f2ba01472> 


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

What is Distroless?
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

Distroless Image
python runtime
application only





Typical DevOps Flow

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

