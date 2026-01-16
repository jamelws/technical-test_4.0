# Technical Test – Answers

## Q1. Explain the functionality of the integration and what it accomplishes.
The integration provides a simple REST API (`/health`) using WSO2 Micro Integrator. Its goal is to create a health check endpoint that validates the availability and readiness of the integration runtime.

The integration is packaged as a Carbon Application (`.car`), allowing automatic deployment when the artifact is mounted into the Micro Integrator runtime. This method reflects a practical DevOps workflow where integration artifacts are built once and deployed consistently across environments.

---

## Q2. Attach a screenshot running “ps aux” command inside the Docker image.
The Docker image is built on the WSO2 Micro Integrator base image and includes the necessary utilities (`tcpdump`, `procps`, and `curl`). The `ps aux` command was run inside a running container to show active processes in the image and confirm that the runtime is working correctly.

(A screenshot of the `ps aux` output is provided as requested.)

---

## Q3. Describe which services run on ports 8290 and 8253.
- **Port 8290**: HTTP transport used by WSO2 Micro Integrator to expose REST APIs and proxy services over HTTP.
- **Port 8253**: HTTPS transport used by WSO2 Micro Integrator to expose REST APIs and proxy services over HTTPS.

These are the default passthrough listener ports for WSO2 Micro Integrator.

---

## Q4. How can you manage observability, security, and availability for the implementation?

### Observability
- Centralized logging using tools like ELK or EFK stacks.
- Metrics collection through Prometheus and visualization with Grafana.
- Health checks and readiness/liveness probes for Kubernetes.
- Distributed tracing with OpenTelemetry when needed.

### Security
- Running containers as a non-root user.
- Using Kubernetes Secrets to manage binary artifacts and sensitive data.
- TLS termination at the Ingress level.
- NetworkPolicies to limit pod-to-pod communication.
- Image immutability ensured by using image digests.

### Availability
- Multiple replicas managed by a Kubernetes Deployment.
- Horizontal Pod Autoscaler (HPA) based on CPU and memory use.
- Rolling updates to prevent downtime during deployments.
- Ingress-based traffic routing with load balancing across replicas.

These practices ensure a reliable, secure, and production-ready deployment that follows DevOps and Kubernetes best practices.