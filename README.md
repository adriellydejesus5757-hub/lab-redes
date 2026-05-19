# lab-redes
# 🐝 Laboratório com Containerlab

> Laboratório prático de **filtragem de pacotes em velocidade de linha** usando **eBPF/XDP** em um ambiente de rede virtualizado com **Containerlab**.

[![Containerlab](https://img.shields.io/badge/Containerlab-v0.50+-blue?logo=linux)](https://containerlab.dev)
[![Docker](https://img.shields.io/badge/Docker-required-blue?logo=docker)](https://www.docker.com)
[![Licença](https://img.shields.io/badge/licença-GPL--2.0-green)](LICENSE)

## 📖 Visão Geral

Este laboratório demonstra um recurso muito "gratuita" em termos de CPU.

**O que este laboratório demonstra:**
- Deploy de uma rede virtual com 2 nós usando Containerlab.
- Bloqueio de tráfego ICMP (ping) em velocidade de linha.

---

## Topologia 

```
┌─────────────────────────────────────────┐
│               Máquina Host              │
│                                         │
│  ┌──────────┐ eth1   eth1 ┌──────────┐  │
│  │  node-a  ├─────────────┤  node-b  │  │
│  │10.0.0.1  │             │10.0.0.2  │  │
│  └──────────┘             └──────────┘  │
│    (emissor)              │
└─────────────────────────────────────────┘
```
