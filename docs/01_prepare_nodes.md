# Prepare nodes

## Environment

### Control Plane

- OS: Rocky Linux 9
- CPU: 2
- RAM: 4 GB

### Worker

- OS: Rocky Linux 9
- CPU: 2
- RAM: 4 GB

## Set hostnames

Master

```bash
hostnamectl set-hostname k8s-master
```

Worker

```bash
hostnamectl set-hostname k8s-worker1
```

## Configure /etc/hosts

```text
192.168.15.17 k8s-master
192.168.15.18 k8s-worker1
```

## Disable swap

```bash
swapoff -a
```

Also comment the swap entry in:

```text
/etc/fstab
```

## Configure SELinux

Temporary:

```bash
setenforce 0
```

Permanent:

```text
SELINUX=permissive
```

## Disable firewall

```bash
systemctl disable firewalld --now
```
