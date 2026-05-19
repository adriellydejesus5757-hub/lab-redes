# lab-redes
# 🐝 Laboratório XDP/eBPF com Containerlab

> Laboratório prático de **filtragem de pacotes em velocidade de linha** usando **eBPF/XDP** em um ambiente de rede virtualizado com **Containerlab**.

[![Containerlab](https://img.shields.io/badge/Containerlab-v0.50+-blue?logo=linux)](https://containerlab.dev)
[![Docker](https://img.shields.io/badge/Docker-required-blue?logo=docker)](https://www.docker.com)
[![eBPF](https://img.shields.io/badge/eBPF-XDP-orange)](https://ebpf.io)
[![Licença](https://img.shields.io/badge/licença-GPL--2.0-green)](LICENSE)

## 📖 Visão Geral

Este laboratório demonstra um recurso muito poderoso do kernel Linux: o **XDP (eXpress Data Path)**. Aqui é anexado um pequeno programa eBPF na interface de rede, que descarta pacotes **antes mesmo que eles cheguem à pilha de rede**, tornando a filtragem praticamente "gratuita" em termos de CPU.

**O que este laboratório demonstra:**
- Compilação de um programa eBPF em C para bytecode BPF usando Docker como ambiente de build.
- Deploy de uma rede virtual com 2 nós usando Containerlab.
- Carregamento de um programa XDP em uma interface de rede com `bpftool`.
- Bloqueio de tráfego ICMP (ping) em velocidade de linha.
- Leitura de contadores de pacotes descartados a partir de um **BPF Map** em tempo real.
- O laboratório disponibiliza um script (ativation-test.md) para testar o deploy e comparar o desempenho do XDP com o iptables.
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
