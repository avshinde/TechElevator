# 🔹 Load Balancing – Advanced Interview Preparation Notes

---

## ✅ What is Load Balancing?

Load Balancing is a method of **distributing incoming network traffic across multiple backend servers** to ensure:

- High availability
- Fault tolerance
- Scalability
- Optimized resource utilization

---

## 🔧 Core Concepts

| Concept | Description |
|--------|-------------|
| **Server Pool** | Group of backend servers that share the load. |
| **Health Checks** | Periodic checks to ensure backend servers are up. |
| **Session Persistence (Sticky Sessions)** | Ties a user session to a specific server. |
| **Failover** | Automatically reroutes traffic if a server fails. |
| **DNS Load Balancing** | Uses DNS resolution to distribute load. |
| **Reverse Proxy** | Often used as a load balancer in front of application servers. |

---

## ⚙️ Load Balancing Algorithms

| Algorithm | Use Case |
|----------|----------|
| **Round Robin** | Equal distribution; good for similar server configs. |
| **Least Connections** | Routes to the server with the fewest active connections. |
| **IP Hash** | Based on client IP for sticky sessions. |
| **Weighted Round Robin / Least Connections** | Prioritizes more powerful servers. |
| **Random** | Randomly distributes to available servers. |

---

## 📐 Architecture & Real-World Use Cases

### 🔸 Scenario 1: Web Application (3-Tier Architecture)
- Client → Nginx/HAProxy Load Balancer → App Servers → DB
- Add auto-scaling groups in cloud environments (AWS/GCP/Azure)

### 🔸 Scenario 2: Microservices with API Gateway
- Client → API Gateway (with built-in load balancing) → Microservices
- Tools: Kong, Istio, AWS API Gateway

---

## 🚀 Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Nginx** | Software-based L4/L7 load balancer |
| **HAProxy** | High-performance L4/L7 load balancer |
| **AWS ELB (ALB/NLB/CLB)** | Cloud-managed load balancing |
| **Kubernetes Ingress Controller** | Load balancing for K8s services |
| **Istio Envoy** | Sidecar load balancing in service mesh |

---

## 🧪 Hands-on Experience Checklist

✅ Configure **Nginx load balancer** for multiple app servers  
✅ Use **HAProxy** to balance HTTP and TCP traffic  
✅ Implement **AWS ALB with ECS/EKS**  
✅ Deploy **Kubernetes Ingress** for service routing  
✅ Use **Terraform or CloudFormation** to provision load balancers  
✅ Configure **health checks** and **sticky sessions**  
✅ Benchmark with tools like **Apache Benchmark**, **JMeter**, or **Locust**

---

## 🔐 Security Considerations

- Use **HTTPS termination** at Load Balancer
- Enable **Web Application Firewall (WAF)**
- Protect against **DDoS** (e.g., via AWS Shield)
- Implement **rate limiting**

---

## 🧠 Interview Angle – Sample Questions

### Q1. How would you design a load-balanced system for millions of users?
- Discuss global load balancing (e.g., Route 53 + Cloudflare), CDN, regional ALBs, and auto-scaling.

### Q2. How do you handle sticky sessions in stateless microservices?
- Use JWT tokens, Redis-backed session storage, or consistent hashing.

### Q3. What’s the difference between Layer 4 and Layer 7 load balancing?
- L4: TCP/UDP-level, faster, no app-layer logic  
- L7: HTTP-level, allows content-based routing, SSL termination

### Q4. How do you handle server failure in a load-balanced setup?
- Health checks, remove failed node from pool, auto-replace in cloud infra

### Q5. How does a load balancer affect scalability and availability?
- Horizontal scalability, fault tolerance, enables zero-downtime deployments

---

## 📊 Diagrams You Can Draw

1. **Load Balancer in front of App Servers**
2. **High Availability Setup with Two Load Balancers (Active-Passive)**
3. **Kubernetes Ingress + LoadBalancer Service**
