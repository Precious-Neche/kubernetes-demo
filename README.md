# Kubernetes Demo Project

This project demonstrates deploying a simple web application with MongoDB on Kubernetes using Deployments, Services, ConfigMaps, and Secrets.

## Project Structure

- **mongo-secret.yaml** – Stores MongoDB credentials as Kubernetes secrets.
- **mongo-config.yaml** – Holds MongoDB configuration like connection URL.
- **mongo.yaml** – Deployment and Service configuration for MongoDB.
- **webapp.yaml** – Deployment and Service configuration for the demo web application.

## Setup Instructions

1. **Clone the repository**  
   ```bash
   git clone(https://github.com/Precious-Neche/kubernetes-demo.git)
   cd Kubernetes-Demo
   ```

2. **Apply MongoDB Secret and ConfigMap**  
   ```bash
   kubectl apply -f mongo-secret.yaml
   kubectl apply -f mongo-config.yaml
   ```

3. **Deploy MongoDB**  
   ```bash
   kubectl apply -f mongo.yaml
   ```

4. **Deploy Web Application**  
   ```bash
   kubectl apply -f webapp.yaml
   ```

5. **Check Deployments and Services**  
   ```bash
   kubectl get all
   ```

6. **Access the Application**  
   The application runs as a NodePort service.  
   Visit:  
   ```
   http://<Node-IP>:30007/
   ```

   Replace `<Node-IP>` with the IP address of your Kubernetes node (for Minikube, use `minikube ip`).

## Notes

- Ensure Kubernetes is running locally or on your preferred cluster.
- The web application depends on MongoDB, so Mongo must be deployed first.
- Update `nodePort` in `webapp.yaml` if port `30007` is unavailable.
