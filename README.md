# DevOps CI/CD Project

Projeto de portfólio demonstrando uma pipeline DevOps completa com containerização, orquestração e observabilidade.

## 🚀 Stack utilizada

- Python (Flask API)
- Docker
- Kubernetes
- Minikube
- Prometheus
- Grafana

## 🏗 Arquitetura

Client → Kubernetes Service → Flask API  
Prometheus → coleta métricas da API  
Grafana → visualiza métricas em dashboards

## 📂 Estrutura do projeto

devops-cicd-project

app/  
 ├── app.py  
 └── requirements.txt  

k8s/  
 ├── deployment.yaml  
 └── service.yaml  

monitoring/  
 ├── prometheus-configmap.yaml  
 ├── prometheus-deployment.yaml  
 ├── prometheus-service.yaml  
 ├── grafana-deployment.yaml  
 └── grafana-service.yaml  

Dockerfile

README.md

## 🐳 Build da aplicação

Build da imagem Docker:

docker build -t devops-api .

Carregar imagem no Minikube:

minikube image load devops-api

## ☸ Deploy no Kubernetes

Aplicar os manifests:

kubectl apply -f k8s/

Verificar pods:

kubectl get pods

## 🌐 Acessar a API

minikube service devops-api-service

Endpoints disponíveis:

/  
/health  
/metrics  

## 📊 Monitoramento

### Prometheus

Deploy:

kubectl apply -f monitoring/

Acessar:

minikube service prometheus-service

Métrica exposta pela aplicação:

app_requests_total

### Grafana

Abrir Grafana:

minikube service grafana-service

Login padrão:

admin / admin

Adicionar Prometheus como datasource:

http://prometheus-service:9090

Criar dashboard com query:

app_requests_total

## 📈 Funcionalidades DevOps demonstradas

- Containerização com Docker
- Orquestração com Kubernetes
- Deploy local com Minikube
- Observabilidade com Prometheus
- Dashboards com Grafana
- Endpoint de health check
- Endpoint de métricas para monitoramento

## 🎯 Objetivo

Este projeto demonstra práticas modernas de DevOps e infraestrutura cloud-native, incluindo deploy de aplicações containerizadas, monitoramento e observabilidade.

## 🔧 Melhorias futuras

- Pipeline CI/CD com GitHub Actions
- Deploy automático no Kubernetes
- Helm charts
- Autoscaling (HPA)
- Deploy em cloud (AWS / GCP)
