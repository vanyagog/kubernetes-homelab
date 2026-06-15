# Kubernetes Homelab

Production-like Kubernetes environment built for learning and demonstrating DevOps and SRE practices.

## Stack

- Kubernetes
- Docker
- Traefik
- PostgreSQL
- Prometheus
- Grafana

## Goals

- Deploy a containerized application
- Configure ingress with Traefik
- Deploy PostgreSQL
- Set up monitoring with Prometheus and Grafana
- Practice Kubernetes manifests and troubleshooting

## Architecture

Internet
↓
Traefik
↓
Demo Application
↓
PostgreSQL

Prometheus
↓
Grafana

## Future improvements

- Helm
- GitLab CI/CD
- Ansible
- Backup automation
