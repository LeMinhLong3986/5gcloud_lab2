# Triển khai Web Tĩnh trên Kubernetes với Minikube

Dự án này minh họa cách triển khai một ứng dụng web tĩnh trên Kubernetes bằng cách sử dụng Minikube và NodePort để truy cập từ bên ngoài.

## Cách thực hiện

1. Khởi động Minikube và đảm bảo nó đang sử dụng Docker driver:
   ```bash
   minikube start --driver=docker
2. Cấu hình Docker Daemon cho Minikube:
   ```bash
   minikube -p minikube docker-env --shell=powershell | Invoke-Expression

3. Build Docker Image:
   ```bash
   docker build -t static-web .

4. Áp dụng cấu hình Deployment trên Kubernetes:
   ```bash
   kubectl apply -f deployment.yaml

5. Áp dụng cấu hình Service trên Kubernetes:
   ```bash
   kubectl apply -f service.yaml

6. Truy cập vào ứng dụng:
   ```bash
   minikube service static-web-service

7. Truy cập vào trang web ở đường dẫn URL dưới dòng "Starting tunnel for service static-web-service" trong Terminal vì sử dụng tunnel (127.0.0.1:port) thường đáng tin cậy hơn trên Windows.