🧩 1. Importar a imagem .OVA

📁 Arquivo: UbuntuServer-OnPremises.ova (na pasta Downloads)

Abra o VirtualBox <br>
Clique em 📂 Arquivo → Importar Appliance<br>
Clique em 📁 e selecione:<br>
Downloads → UbuntuServer-OnPremises.ova<br>
Clique em ➡️ Próximo<br>
Revise as configurações (não altere nada por enquanto)<br>
Clique em ✅ Importar<br>

⏳ Aguarde (pode levar alguns minutos)

🌐 2. Configurar rede em modo Bridge (Ponte)
Selecione a VM importada
Clique em ⚙️ Configurações
Vá até 🌐 Rede
Em Adaptador 1:
✔️ Marque: Habilitar Placa de Rede
🔽 Conectado a: Placa em modo Bridge
🔽 Nome: escolha a placa de rede cabeada
(geralmente algo como Ethernet, Realtek, Intel(R) Ethernet)

📌 Importante:

NÃO use Wi-Fi
Use a interface de rede física do laboratório
Clique em OK
▶️ 3. Iniciar a máquina virtual
Selecione a VM
Clique em ▶️ Iniciar

⏳ Aguarde o boot do Ubuntu Server

🔍 4. Descobrir o endereço IP da VM

Na tela da VM, faça login (credenciais fornecidas pelo professor) e execute:

ip a

Procure por algo como:

inet 192.168.x.x

📌 Esse será o IP para acesso remoto

🔐 5. Acessar via SSH

No Windows (Prompt ou PowerShell):

ssh usuario@IP_DA_VM

Exemplo:

ssh aluno@192.168.0.50
✅ 6. Teste de conectividade

Se não conectar:

Verifique se o IP foi obtido:
ip a
Teste rede:
ping 8.8.8.8
Verifique o SSH:
sudo systemctl status ssh

Se necessário:

sudo systemctl start ssh
⚠️ Dicas importantes
🔌 O cabo de rede deve estar conectado
🏫 A rede do laboratório precisa liberar DHCP
🔒 Firewall do Windows pode bloquear SSH (raro, mas possível)
🔄 Se não pegar IP, reinicie a VM

Se quiser, posso te passar também:

✔️ Como fixar IP na VM
✔️ Como acessar via PuTTY
✔️ Como integrar essa VM com exercícios de IA nas próximas aulas
Agora preciso importar uma imagem da máquina virtual do GNU/Linux Ubuntu Server 22.04.4 LTS desenvolvida pelo Professor Robson Vaamonde no Oracle Virtualbox versão 7.2 já instalado e configurado nos computadores do laboratório de informática da unidade, o sistema operacional dos laboratórios é o Microsoft Windows 11, armazenamento de 1 terá, 32gb ram, intel(r) core (tm) i7-14700k, essa imagem já foi disponibilizada pelo Professor para fazer o download e está disponível na pasta Downloads com o nome de UbuntuServer-Container.ova, essa imagem será utilizada em todas as aulas práticas de IA. Para isso preciso de um passo a passo detalhado (Simples, Objetivo, Direto e pode usar Ícones para facilitar o entendimento) mostrando como importar essa imagem e configurar a rede em modo Bridge (Ponte) utilizando a rede cabeada local do laboratório e no final iniciar a máquina virtual para acesso remoto via SSH.

Segue o procedimento objetivo para sua nova VM (UbuntuServer-Container.ova) no Oracle VM VirtualBox rodando em Windows 11.

🧩 1. Importar a imagem .OVA

📁 Arquivo: Downloads → UbuntuServer-Container.ova

Abra o VirtualBox
Clique em 📂 Arquivo → Importar Appliance
Clique em 📁 e selecione:
UbuntuServer-Container.ova
Clique em ➡️ Próximo
(Opcional) Ajuste recursos conforme o hardware disponível:
🧠 RAM: 4096 MB ou mais
🧮 CPU: 2 a 4 núcleos (se permitido)
Clique em ✅ Importar

⏳ Aguarde a finalização

🌐 2. Configurar rede em modo Bridge (Ponte)
Selecione a VM importada
Clique em ⚙️ Configurações
Acesse 🌐 Rede → Adaptador 1

Configure:

✔️ Habilitar Placa de Rede
🔽 Conectado a: Placa em modo Bridge
🔽 Nome: selecione a interface cabeada:
Ethernet
Intel(R) Ethernet
Realtek PCIe

📌 Regras:

❌ Não usar Wi-Fi
✔️ Usar rede física do laboratório
Clique em OK
▶️ 3. Iniciar a VM
Selecione a máquina
Clique em ▶️ Iniciar

⏳ Aguarde o boot do Ubuntu Server

🔍 4. Obter o endereço IP

Após login no sistema:

ip a

Identifique:

inet 192.168.X.X

📌 Esse IP será usado no SSH

🔐 5. Acesso remoto via SSH

No Windows (Prompt ou PowerShell):

ssh usuario@IP_DA_VM

Exemplo:

ssh aluno@192.168.1.100
🧪 6. Verificações essenciais

Dentro da VM:

Testar rede
ping 8.8.8.8
Verificar SSH
sudo systemctl status ssh

Se necessário:

sudo systemctl enable ssh
sudo systemctl start ssh
⚙️ Observações sobre o ambiente do laboratório

Com seu hardware:

💾 1 TB armazenamento
🧠 32 GB RAM
⚡ Intel i7-14700K

Você pode, se permitido:

Rodar múltiplas VMs
Aumentar RAM (8GB+) para containers
Usar Docker/Kubernetes sem limitação relevante
⚠️ Problemas comuns
❌ VM sem IP → Bridge configurado errado
❌ Sem internet → interface errada selecionada
❌ SSH não conecta → serviço não iniciado
❌ IP muda → DHCP da rede (normal)

---

🧩 1. Importar a imagem .OVA

No Oracle VM VirtualBox:

Abra o VirtualBox
Clique em 📂 Arquivo → Importar Appliance
Selecione:
Downloads → UbuntuServer-Container.ova
Clique em ➡️ Próximo
⚙️ 2. Ajustar recursos (IMPORTANTE no seu caso)

Antes de importar, ajuste:

🧠 Memória RAM
Recomendado: 8192 MB (8 GB)
Pode usar até: 12288 MB (12 GB) (se for usar containers pesados)
🧮 Processador
Recomendado: 4 CPUs
Pode usar até: 6–8 CPUs (sem prejudicar o Windows)
💾 Disco
Manter padrão (ou expandir depois se necessário)

📌 Evite usar mais de 50% dos recursos totais para manter estabilidade

Clique em ✅ Importar
🌐 3. Configurar rede Bridge (Ponte)
Selecione a VM
Clique em ⚙️ Configurações → Rede
Adaptador 1:
✔️ Habilitar Placa de Rede
🔽 Conectado a: Placa em modo Bridge
🔽 Nome: escolha a placa cabeada:
Ethernet
Intel(R) Ethernet

📌 Regras críticas:

❌ Não usar Wi-Fi
✔️ Usar rede física do laboratório
Clique em OK
▶️ 4. Iniciar a VM
Selecione a VM
Clique em ▶️ Iniciar

⏳ Aguarde o boot do Ubuntu Server

🔍 5. Descobrir o IP da VM

Após login:

ip a

Procure por:

inet 192.168.X.X
🔐 6. Acesso via SSH

No Windows 11:

ssh usuario@IP_DA_VM

Exemplo:

ssh aluno@192.168.0.120
🧪 7. Testes básicos
Testar internet:
ping 8.8.8.8
Verificar SSH:
sudo systemctl status ssh

Se necessário:

sudo systemctl enable ssh
sudo systemctl start ssh
🚀 Otimizações recomendadas para seu hardware

Com essa máquina, você pode ir além:

📦 Para containers (Docker/Kubernetes)
RAM: 12 GB
CPU: 6+ cores
🔁 Para múltiplas VMs
Criar 2–3 VMs simultâneas sem travar o sistema
⚡ Desempenho
Ativar Paravirtualização (KVM):
Configurações → Sistema → Aceleração
⚠️ Problemas comuns
❌ VM não pega IP → Bridge na interface errada
❌ SSH falha → serviço não ativo
❌ Lentidão → alocou RAM/CPU demais
❌ Sem rede → cabo desconectado

---

📡 Tabela de Configuração de Rede
| 🖥️ Servidor        | 🌐 Endereço IP   | 🧮 Máscara         | 🚪 Gateway      | 🔎 DNS           | 📝 Observação              |
|-------------------|------------------|--------------------|----------------|------------------|---------------------------|
| 🖥️ Server01       | 10.24.82.10      | 255.255.255.0      | 10.24.82.1     | 10.24.40.190     | Servidor principal        |
| 🖥️ Server02       | 10.24.82.11      | 255.255.255.0      | 10.24.82.1     | 10.24.40.190     | Servidor secundário       |
📌 Critérios adotados
Faixa válida da rede: 10.24.82.1 – 10.24.82.254
.1 reservado para gateway (já definido)
IPs baixos (.10, .11) escolhidos para facilitar identificação e evitar conflitos
Endereços estáticos recomendados para servidores

---
