# Install containerd

## Install packages

```bash
dnf install -y yum-utils device-mapper-persistent-data lvm2
```

## Add Docker repository

```bash
dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

## Install containerd

```bash
dnf install -y containerd.io
```

## Generate configuration

```bash
mkdir -p /etc/containerd

containerd config default > /etc/containerd/config.toml
```

Set:

```text
SystemdCgroup = true
```

## Enable service

```bash
systemctl enable containerd --now
```

## Load kernel modules

```bash
modprobe overlay

modprobe br_netfilter
```

## Configure sysctl

```bash
cat <<EOF >/etc/sysctl.d/k8s.conf
net.bridge.bridge-nf-call-iptables=1
net.bridge.bridge-nf-call-ip6tables=1
net.ipv4.ip_forward=1
EOF

sysctl --system
```
