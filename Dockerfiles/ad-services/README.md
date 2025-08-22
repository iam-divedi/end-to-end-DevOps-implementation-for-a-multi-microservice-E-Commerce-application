# 🌟 OpenTelemetry Demo – Ad Service

This repository contains the **Ad Service**, a Java-based microservice that is part of the [OpenTelemetry Demo](https://opentelemetry.io/).  
It simulates an advertising component and is used to demonstrate **distributed tracing, metrics, and logging** in a microservices environment.  

The service is built with **Java 21 (Eclipse Temurin)** and **Gradle**, packaged into a self-contained distribution, and shipped with a ready-to-use **Dockerfile** for seamless deployment. 🚀  

# 🌟 OpenTelemetry Demo – Ad Service

This repository contains the **Ad Service**, a Java-based microservice that is part of the [OpenTelemetry Demo](https://opentelemetry.io/).  
It simulates an advertising component and is used to demonstrate **distributed tracing, metrics, and logging** in a microservices environment.  

The service is built with **Java 21 (Eclipse Temurin)** and **Gradle**, packaged into a self-contained distribution, and shipped with a ready-to-use **Dockerfile** for seamless deployment. 🚀  

---

## 🔧 How It Works

The project uses a **multi-stage Docker build** for efficiency:

1. **Builder Stage** (`eclipse-temurin:21-jdk`)  
   - Prepares Gradle wrapper and downloads dependencies  
   - Compiles Java sources and Protocol Buffers  
   - Creates a runnable distribution with `installDist`  

2. **Runtime Stage** (`eclipse-temurin:21-jre`)  
   - Copies only the compiled application  
   - Runs the Ad Service using the generated startup script  

👉 This approach keeps the final Docker image **lightweight, fast, and production-ready**.  



```bash
# Step 1: Build the image
docker build -t ad-service .

# Step 2: Run the container (default port 9099)
docker run -d -p 9099:9099 --name ad-service ad-service

# Step 3: Verify service is running
curl http://localhost:9099

