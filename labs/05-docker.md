
# 📋 Documentação Técnica — Servidor GNU/Linux Ubuntu Server

> **Documento gerado para fins de auditoria e gestão de ativos**
> Data de coleta: 2026 | Servidor: `ctlinux01`

---

## 🖥️ 1. Informações Gerais do Servidor

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| 🏷️ Geral | Nome do Servidor (Hostname) | `ctlinux01` |
| 🐧 Geral | Sistema Operacional | Ubuntu 24.04.4 LTS (Noble Numbat) |
| 🔢 Geral | Versão do Kernel | Linux 6.8.0-106-generic |
| 🏗️ Geral | Arquitetura | x86-64 (64 bits) |
| 🪪 Geral | Machine ID | `05c2865e767d44c4870777b482ba0652` |
| 🔄 Geral | Boot ID (sessão atual) | `b7cbfed64a9e41708f3f2f9bc8fffc31` |
| ⏱️ Geral | Tempo de Atividade (Uptime) | 41 minutos (no momento da coleta) |
| 👤 Geral | Usuários Logados | 1 usuário |
| 📊 Geral | Carga do Sistema (Load Average) | 0.10 / 0.21 / 0.16 (1, 5, 15 min) |

> 💬 **Para o time de gestão:** Este é um servidor Linux com o nome `ctlinux01`. Ele estava há apenas 41 minutos em operação no momento do levantamento, o que indica que pode ter sido reiniciado recentemente. A carga de trabalho está baixa — o servidor está trabalhando com folga.

---

## ⚙️ 2. Informações de Hardware do Servidor

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| 🖥️ Hardware | Tipo de Máquina | Máquina Virtual (VM) |
| 🏭 Hardware | Fabricante do Hardware | innotek GmbH |
| 📦 Hardware | Modelo | VirtualBox |
| 🔧 Hardware | Plataforma de Virtualização | Oracle VirtualBox |
| 🧠 Hardware | Memória RAM Total | 3.915 MB (~4 GB) |
| 🧠 Hardware | Memória RAM Utilizada | 522 MB |
| 🧠 Hardware | Memória RAM Disponível | 3.393 MB |
| 💾 Hardware | Swap Total | 3.914 MB (~4 GB) |
| 💾 Hardware | Swap Utilizado | 0 MB |
| 🗄️ Hardware | Disco Principal (sda) | 50 GB (tipo: disco virtual) |
| 📂 Hardware | Partição de Boot (`/boot`) | 2 GB — 198 MB usados (11%) |
| 📂 Hardware | Volume Principal LVM (`/`) | 48 GB — 8,5 GB usados (19%) |
| 💿 Hardware | Leitor óptico (sr0) | 1024 MB (ROM) |
| 🗂️ Hardware | Tipo de Gerenciamento de Volume | LVM (ubuntu-vg/ubuntu-lv) |
| 📅 Hardware | Data do Firmware | 01/12/2006 |

> 💬 **Para o time de gestão:** Este servidor **não é físico** — ele roda dentro de outro computador usando um software chamado VirtualBox (tecnologia da Oracle). Possui cerca de **4 GB de memória RAM**, dos quais apenas 13% estão em uso — confortável por enquanto. O disco principal tem **50 GB**, com apenas 19% ocupado, e há bastante espaço disponível. O Swap (memória de reserva) está zerado, o que é um bom sinal de saúde do sistema.

---

## 🌐 3. Informações de Rede do Servidor

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| 🌐 Rede | Status de Conectividade | Online ✅ |
| 🔌 Rede | Interface Principal | `enp0s3` (Ethernet — Intel Corporation) |
| 🏠 Rede | Endereço IPv4 | `10.24.82.225/24` |
| 📡 Rede | Endereço IPv6 (link local) | `fe80::a00:27ff:fe3d:1d6a/64` |
| 🔲 Rede | MAC Address (enp0s3) | `08:00:27:3d:1d:6a` |
| 🚪 Rede | Gateway Padrão (rota de saída) | `10.24.82.1` |
| 🔁 Rede | Interface Loopback | `lo` — `127.0.0.1/8` |
| 🐋 Rede | Interface Docker (Bridge) | `docker0` — `172.17.0.1/16` |
| 🔗 Rede | Interface Virtual Docker | `vethe3405be` (conectada ao docker0) |
| 🧭 Rede | Servidor DNS Primário | `8.8.8.8` (Google) |
| 🧭 Rede | Servidor DNS Secundário | `8.8.4.4` (Google) |
| 🔒 Rede | Modo DNS Resolver | Stub (systemd-resolved) |
| 🚫 Rede | LLMNR / mDNS / DNSOverTLS | Desativados |
| 🔓 Rede | DNSSEC | Não suportado |

### 🔌 Portas Abertas e em Escuta (Listening)

| Categoria | Porta | Protocolo | Endereço | Descrição |
|-----------|-------|-----------|----------|-----------|
| 🔐 Rede | `22` | TCP | `0.0.0.0` | SSH — Acesso remoto ao servidor |
| 🐋 Rede | `9000` | TCP | `0.0.0.0` e `[::]` | Portainer — Painel de gerenciamento Docker |
| 🧭 Rede | `53` | TCP | `127.0.0.53` e `127.0.0.54` | DNS local (systemd-resolved) |

> 💬 **Para o time de gestão:** O servidor está na rede com o endereço IP `10.24.82.225`. Ele usa os servidores DNS do Google para resolver nomes de sites e sistemas. Há uma rede interna exclusiva para os contêineres Docker (`172.17.0.0/16`). Apenas **3 serviços** estão aceitando conexões externas: acesso remoto via SSH (porta 22) e o painel de gerenciamento Portainer (porta 9000). O Portainer é a ferramenta visual para gerenciar os contêineres Docker.

---

## ⚙️ 4. Informações de Serviços e Processos

| Categoria | Serviço | Status | Descrição |
|-----------|---------|--------|-----------|
| 🐋 Serviço | `docker.service` | ✅ Ativo | Motor principal do Docker |
| 🐋 Serviço | `containerd.service` | ✅ Ativo | Runtime de contêineres (suporte ao Docker) |
| 🐋 Serviço | `portainer.service` | ✅ Ativo | Painel web de gerenciamento Docker |
| 🔐 Serviço | `ssh.service` | ✅ Ativo | Acesso remoto seguro ao servidor |
| 🌐 Serviço | `systemd-networkd.service` | ✅ Ativo | Gerenciamento de interfaces de rede |
| 🧭 Serviço | `systemd-resolved.service` | ✅ Ativo | Resolução de nomes DNS |
| ⏰ Serviço | `systemd-timesyncd.service` | ✅ Ativo | Sincronização de horário via rede (NTP) |
| 📋 Serviço | `rsyslog.service` | ✅ Ativo | Registro de logs do sistema |
| 🔄 Serviço | `cron.service` | ✅ Ativo | Agendamento de tarefas automáticas |
| 🔒 Serviço | `polkit.service` | ✅ Ativo | Controle de permissões e autorização |
| 🔌 Serviço | `dbus.service` | ✅ Ativo | Comunicação entre processos do sistema |
| 💾 Serviço | `udisks2.service` | ✅ Ativo | Gerenciamento de discos |
| 🔌 Serviço | `multipathd.service` | ✅ Ativo | Controle de múltiplos caminhos de disco |
| 📱 Serviço | `ModemManager.service` | ✅ Ativo | Gerenciamento de modems |
| 🔋 Serviço | `upower.service` | ✅ Ativo | Gerenciamento de energia |
| 🔧 Serviço | `fwupd.service` | ✅ Ativo | Atualizações de firmware |
| 🖥️ Serviço | `getty@tty1.service` | ✅ Ativo | Terminal local (console físico) |
| 👤 Serviço | `systemd-logind.service` | ✅ Ativo | Gerenciamento de sessões de usuário |
| 📦 Serviço | `systemd-udevd.service` | ✅ Ativo | Gerenciamento de dispositivos de hardware |
| 🔄 Serviço | `unattended-upgrades.service` | ✅ Ativo | Atualizações automáticas de segurança |
| 📊 Serviço | `user@1000.service` | ✅ Ativo | Sessão do usuário logado (UID 1000) |

> 💬 **Para o time de gestão:** O servidor está rodando **22 serviços ativos**, todos em perfeito funcionamento. Os principais para este ambiente são o **Docker** (que executa os contêineres/aplicações), o **Portainer** (painel web acessível pela porta 9000 para gerenciar os contêineres visualmente sem precisar de comandos), e o **SSH** (para acesso remoto de administradores). O sistema também atualiza automaticamente patches de segurança, o que é uma boa prática.

---

## 📦 5. Informações de Atualizações de Software

> Total de pacotes com atualização disponível: **57 pacotes**

### 🐋 Atualizações Relacionadas ao Docker

| Categoria | Pacote | Versão Atual | Versão Disponível |
|-----------|--------|-------------|-------------------|
| 🐋 Docker | `docker-ce` | 5:29.2.1 | **5:29.4.0** |
| 🐋 Docker | `docker-ce-cli` | 5:29.2.1 | **5:29.4.0** |
| 🐋 Docker | `docker-ce-rootless-extras` | 5:29.2.1 | **5:29.4.0** |
| 🐋 Docker | `docker-buildx-plugin` | 0.31.1 | **0.33.0** |
| 🐋 Docker | `docker-compose-plugin` | 5.1.0 | **5.1.1** |
| 🐋 Docker | `containerd.io` | 2.2.1 | **2.2.2** |

### 🔒 Atualizações de Segurança Críticas

| Categoria | Pacote | Versão Atual | Versão Disponível |
|-----------|--------|-------------|-------------------|
| 🔐 Segurança | `openssl` | 3.0.13-0ubuntu3.7 | **3.0.13-0ubuntu3.9** |
| 🔐 Segurança | `libssl3t64` | 3.0.13-0ubuntu3.7 | **3.0.13-0ubuntu3.9** |
| 🔐 Segurança | `python3-openssl` | 23.2.0-1 | **23.2.0-1ubuntu0.1** |
| 🔐 Segurança | `python3-jwt` | 2.7.0-1 | **2.7.0-1ubuntu0.1** |
| 🔐 Segurança | `python3-pyasn1` | 0.4.8-4ubuntu0.1 | **0.4.8-4ubuntu0.2** |
| 🔐 Segurança | `libtiff6` | 4.5.1-4ubuntu2.4 | **4.5.1-4ubuntu2.5** |
| 🔐 Segurança | `libarchive13t64` | 3.7.2-2ubuntu0.5 | **3.7.2-2ubuntu0.6** |

### 🐧 Atualizações do Sistema Operacional (Kernel e Systemd)

| Categoria | Pacote | Versão Atual | Versão Disponível |
|-----------|--------|-------------|-------------------|
| 🐧 Sistema | `linux-generic` (Kernel) | 6.8.0-106.106 | **6.8.0-107.107** |
| 🐧 Sistema | `linux-image-generic` | 6.8.0-106.106 | **6.8.0-107.107** |
| 🐧 Sistema | `linux-headers-generic` | 6.8.0-106.106 | **6.8.0-107.107** |
| 🐧 Sistema | `systemd` | 255.4-1ubuntu8.12 | **255.4-1ubuntu8.15** |
| 🐧 Sistema | `systemd-resolved` | 255.4-1ubuntu8.12 | **255.4-1ubuntu8.15** |
| 🐧 Sistema | `systemd-timesyncd` | 255.4-1ubuntu8.12 | **255.4-1ubuntu8.15** |
| 🐧 Sistema | `coreutils` | 9.4-3ubuntu6.1 | **9.4-3ubuntu6.2** |
| 🐧 Sistema | `tzdata` | 2025b | **2026a** |
| 🐧 Sistema | `netplan.io` | 1.1.2-8ubuntu1~24.04.1 | **1.1.2-8ubuntu1~24.04.2** |

> 💬 **Para o time de gestão:** Existem **57 pacotes de software** aguardando atualização neste servidor. Entre eles destacam-se atualizações importantes de **segurança** (OpenSSL — componente que protege comunicações criptografadas) e uma nova versão do **Kernel Linux** (o núcleo do sistema operacional). O Docker também tem atualizações disponíveis. Recomenda-se agendar uma janela de manutenção para aplicar essas atualizações em breve, especialmente as de segurança, para manter o servidor protegido.

---

*📄 Documento gerado com base na coleta manual de informações do servidor `ctlinux01` — Ubuntu Server 24.04.4 LTS*
