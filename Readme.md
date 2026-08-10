# 🖥️ LegacyTechLab — Transformando Hardware Legado em um Laboratório de TI

> Projeto de reaproveitamento e modernização tecnológica de hardware legado, transformando um notebook antigo em uma plataforma prática para estudos e experimentos em **Linux, Redes, Infraestrutura de TI, Cloud e Cibersegurança**.

---

## 📌 Sobre o projeto

O **LegacyTechLab** nasceu com dois objetivos principais:

1. **Criar um laboratório prático de Linux e Infraestrutura de TI**;
2. **Reaproveitar hardware legado em um contexto tecnológico atual**, explorando diferentes tecnologias e conceitos de TI.

A proposta é demonstrar que um equipamento antigo, mesmo possuindo limitações de processamento e recursos, ainda pode ser utilizado como uma **plataforma de aprendizagem, experimentação e troubleshooting**.

O projeto começou com a análise de diferentes distribuições Linux e evoluiu para a preparação de um ambiente com **Xubuntu 24.04**, utilizando o notebook como base para futuros laboratórios.

A ideia, entretanto, vai além da instalação de um sistema operacional.

O notebook será utilizado como uma plataforma para explorar diferentes áreas da tecnologia:

```text
                    LegacyTechLab
                         │
              Hardware Legado
                         │
                         ▼
                  Linux / Xubuntu
                         │
        ┌────────────────┼────────────────┐
        │                │                │
       Redes        Infraestrutura      Linux
        │                │                │
        └────────────────┼────────────────┘
                         │
              ┌──────────┴──────────┐
              │                     │
            Cloud             Cibersegurança
```

---

# 🎯 Objetivos

## Objetivo principal

Transformar um equipamento de hardware legado em uma **plataforma de laboratório para aprendizagem prática de tecnologias de TI**.

## Objetivos específicos

### 🐧 Linux

- Instalar e configurar Linux;
- compreender o processo de boot;
- trabalhar com terminal;
- estudar Bash;
- administrar usuários e permissões;
- trabalhar com processos e serviços;
- analisar logs;
- realizar troubleshooting.

### 🌐 Redes

- Configuração TCP/IP;
- endereçamento IP;
- DNS;
- DHCP;
- SSH;
- diagnóstico de conectividade;
- análise de tráfego;
- conceitos de roteamento.

### 🏗️ Infraestrutura

- Serviços Linux;
- administração de sistemas;
- armazenamento;
- automação;
- monitoramento;
- gerenciamento de recursos;
- troubleshooting de infraestrutura.

### ☁️ Cloud

A infraestrutura física do laboratório será utilizada como ambiente de preparação para estudos de cloud computing, incluindo:

- ferramentas CLI;
- conceitos de infraestrutura;
- armazenamento;
- IAM;
- automação;
- monitoramento;
- integração entre ambiente local e serviços cloud.

> A utilização de serviços Cloud não depende necessariamente da capacidade computacional do notebook. O equipamento será utilizado como **estação de administração, laboratório e cliente**, enquanto os recursos computacionais podem ser fornecidos por plataformas cloud.

### 🔐 Cibersegurança

O laboratório também poderá ser utilizado para estudos controlados de:

- hardening Linux;
- gerenciamento de usuários;
- permissões;
- firewall;
- SSH;
- logs;
- auditoria;
- análise de serviços;
- identificação de vulnerabilidades;
- segurança de redes.

Todos os testes de segurança serão realizados em ambientes próprios e controlados.

---

# 🖥️ Hardware do laboratório

| Componente | Especificação |
|---|---|
| Notebook | Positivo Premium Select 7050 |
| Processador | Intel Core i3 de 1ª geração |
| Memória RAM | 8 GB DDR3 |
| SSD | Aproximadamente 240 GB |
| Armazenamento adicional | HD para arquivos pessoais |
| Sistema existente | Windows |
| Sistema Linux planejado | Xubuntu 24.04 |
| Interface gráfica | Xfce |

O equipamento representa deliberadamente um cenário de **hardware limitado/legado**.

Isso permite estudar uma questão relevante de infraestrutura:

> **Como extrair utilidade tecnológica de recursos computacionais que já não são adequados para os padrões atuais de desktops?**

---

# 💡 Conceito do projeto

O LegacyTechLab trabalha com a ideia de:

```text
Hardware antigo
      ↓
Avaliação técnica
      ↓
Escolha de software adequado
      ↓
Modernização
      ↓
Laboratório
      ↓
Experimentação
      ↓
Documentação
      ↓
Conhecimento técnico
```

O hardware não é considerado apenas um equipamento antigo.

Ele é tratado como uma **plataforma de experimentação**.

---

# 🧩 Por que reaproveitar hardware legado?

Equipamentos antigos normalmente apresentam limitações relacionadas a:

- processamento;
- memória;
- armazenamento;
- compatibilidade;
- suporte a tecnologias modernas.

Por outro lado, essas limitações também podem ser utilizadas como oportunidade de aprendizado.

Um ambiente com recursos restritos força decisões relacionadas a:

- eficiência;
- gerenciamento de recursos;
- escolha de software;
- otimização;
- monitoramento;
- troubleshooting;
- arquitetura.

Esses conhecimentos são relevantes para profissionais de infraestrutura mesmo quando trabalham posteriormente com ambientes muito mais modernos.

---

# 🐧 Primeiro laboratório: Linux

A primeira etapa do LegacyTechLab é a criação de um ambiente Linux.

Inicialmente foram avaliadas alternativas como:

- Debian 12;
- Ubuntu;
- Xubuntu.

Após considerar o hardware disponível e o objetivo do laboratório, o projeto foi direcionado para:

## Xubuntu 24.04

A escolha está relacionada principalmente ao ambiente gráfico **Xfce**, buscando uma experiência adequada às limitações do equipamento.

O Xubuntu representa a **primeira camada de software do laboratório**, e não o objetivo final do projeto.

---

# 💾 Arquitetura inicial

A arquitetura planejada inicialmente é:

```text
┌───────────────────────────────────────┐
│              Notebook                 │
│        Positivo Premium Select 7050   │
├───────────────────────────────────────┤
│                                       │
│  SSD ~240 GB                          │
│  ├── Windows                          │
│  └── Xubuntu 24.04                    │
│                                       │
├───────────────────────────────────────┤
│                                       │
│  HD separado                          │
│  └── Arquivos pessoais                │
│                                       │
└───────────────────────────────────────┘
```

O objetivo inicial é implementar **dual boot**, mantendo o Windows existente.

O HD utilizado para arquivos pessoais deverá permanecer preservado durante todo o processo.

---

# 🔎 Diagnóstico inicial

Antes da instalação foram realizadas análises do ambiente.

## Modo de inicialização

Foi identificado:

```text
BIOS: Legacy / Herdado
```

## Tabela de partição

Foi identificado:

```text
Disklabel type: dos
```

Esse resultado indica uma estrutura compatível com **DOS/MBR**.

Essas informações foram importantes para determinar a estratégia de preparação da mídia e do futuro processo de instalação.

---

# 💽 Armazenamento

Durante o diagnóstico foram observados aproximadamente:

```text
Espaço utilizado: 53,8 GB
Espaço livre:     168 GB
Capacidade:       222 GB
```

Esses dados foram utilizados para avaliar a possibilidade de instalar Linux preservando o sistema Windows.

---

# 🛠️ Troubleshooting

O LegacyTechLab também funciona como um projeto de **troubleshooting documentado**.

Durante a criação da mídia USB utilizando o Rufus foram encontrados diferentes problemas.

## Rufus — DBX

Foi apresentada uma mensagem relacionada à atualização dos arquivos **DBX**, utilizados nas verificações de revogação do UEFI Secure Boot.

O equipamento, entretanto, foi identificado como utilizando BIOS Legacy, portanto a mensagem foi analisada dentro do contexto específico do ambiente.

---

## Rufus — GRUB

Também foi apresentada uma mensagem relacionada à versão do GRUB:

```text
Esta imagem usa o Grub 2.12,
mas este aplicativo inclui somente os arquivos
de instalação para Grub 2.14.
```

A ocorrência foi registrada para investigação da compatibilidade entre:

- ISO;
- Rufus;
- GRUB;
- modo de boot;
- estrutura da imagem.

---

## Rufus — erro `0xC0030003`

Durante uma tentativa de criação da mídia foi apresentado:

```text
Erro: [0xC0030003]
```

Também foi registrado:

```text
unable to create file [0x00000003]
```

A criação da mídia foi considerada incompleta até que o processo pudesse ser concluído e validado através de um boot real.

---

# 🧪 Metodologia de troubleshooting

O laboratório segue uma abordagem baseada em diagnóstico:

```text
Problema
   ↓
Coleta de informações
   ↓
Hipótese
   ↓
Teste controlado
   ↓
Registro
   ↓
Análise do resultado
   ↓
Nova hipótese
```

O objetivo não é simplesmente "fazer funcionar".

O objetivo é entender:

> **Por que não funcionou?**

E posteriormente:

> **O que foi alterado para funcionar?**

Essa documentação será mantida no repositório para que cada problema se transforme em conhecimento reutilizável.

---

# 🗺️ Roadmap

## Fase 1 — Recuperação e diagnóstico

- [x] Identificar hardware
- [x] Identificar CPU
- [x] Identificar RAM
- [x] Identificar armazenamento
- [x] Identificar modo de boot
- [x] Identificar tabela de partição
- [x] Avaliar espaço disponível
- [x] Registrar problemas encontrados

## Fase 2 — Linux

- [x] Comparar distribuições
- [x] Definir Xubuntu
- [ ] Criar mídia USB funcional
- [ ] Inicializar ambiente Live
- [ ] Instalar Xubuntu
- [ ] Configurar sistema
- [ ] Validar dual boot
- [ ] Documentar administração básica

## Fase 3 — Redes

- [ ] Configuração TCP/IP
- [ ] Diagnóstico de conectividade
- [ ] DNS
- [ ] DHCP
- [ ] SSH
- [ ] Routing
- [ ] Análise de tráfego

## Fase 4 — Infraestrutura

- [ ] Serviços Linux
- [ ] Servidor SSH
- [ ] Compartilhamento de arquivos
- [ ] Monitoramento
- [ ] Automação Bash
- [ ] Gerenciamento de recursos

## Fase 5 — Cloud

- [ ] CLI de provedor Cloud
- [ ] IAM
- [ ] Armazenamento Cloud
- [ ] Monitoramento
- [ ] Automação
- [ ] Integração entre ambiente local e Cloud

## Fase 6 — Cibersegurança

- [ ] Hardening Linux
- [ ] Firewall
- [ ] Segurança SSH
- [ ] Auditoria de logs
- [ ] Análise de serviços
- [ ] Monitoramento
- [ ] Laboratórios de segurança controlados

---

# 📊 Status atual

**🟡 Em desenvolvimento**

### Concluído

- [x] Definição do conceito do LegacyTechLab
- [x] Identificação do hardware
- [x] Análise inicial das limitações
- [x] Comparação de distribuições Linux
- [x] Escolha inicial do Xubuntu 24.04
- [x] Identificação do BIOS Legacy
- [x] Identificação do particionamento DOS/MBR
- [x] Análise inicial do armazenamento
- [x] Investigação com `fdisk`
- [x] Registro dos problemas do Rufus
- [x] Registro das mensagens relacionadas ao GRUB

### Em andamento

- [ ] Resolver criação da mídia USB
- [ ] Realizar boot pelo USB
- [ ] Testar Xubuntu
- [ ] Planejar particionamento
- [ ] Instalar Linux
- [ ] Configurar dual boot

---

# 🧰 Tecnologias e conceitos

### Sistemas Operacionais

`Linux` `Xubuntu` `Ubuntu` `Debian` `Windows`

### Infraestrutura

`IT Infrastructure` `Storage` `Partitioning` `BIOS` `MBR` `GRUB` `Dual Boot`

### Redes

`TCP/IP` `DNS` `DHCP` `SSH` `Routing`

### Cloud

`Cloud Computing` `CLI` `IAM` `Cloud Storage` `Automation` `Monitoring`

### Cibersegurança

`Linux Hardening` `Firewall` `SSH Security` `Logs` `Auditing` `Network Security`

### Troubleshooting

`Rufus` `USB Boot` `GRUB` `Hardware Troubleshooting` `System Troubleshooting`

---

# 📁 Estrutura do repositório

```text
LegacyTechLab/
│
├── README.md
│
├── docs/
│   ├── 01-contexto-do-laboratorio.md
│   ├── 02-analise-do-hardware.md
│   ├── 03-comparativo-das-distribuicoes.md
│   ├── 04-planejamento-dual-boot.md
│   ├── 05-diagnostico-boot-e-disco.md
│   ├── 06-troubleshooting-rufus.md
│   ├── 07-erros-e-investigacoes.md
│   └── 08-instalacao-xubuntu.md
│
├── labs/
│   ├── linux/
│   ├── networking/
│   ├── infrastructure/
│   ├── cloud/
│   └── cybersecurity/
│
├── logs/
│   └── tentativas-rufus.md
│
├── screenshots/
│   └── README.md
│
└── .gitignore
```

---

# 📚 Documentação

A documentação detalhada será organizada em `docs/`.

Cada etapa deverá registrar:

- objetivo;
- ambiente;
- procedimento;
- comandos utilizados;
- resultado;
- problemas encontrados;
- solução;
- aprendizados.

Os laboratórios práticos serão organizados em `labs/`.

Isso permitirá separar:

**Documentação do ambiente**

de

**Experimentos realizados no ambiente.**

---

# 🌱 Evolução planejada

O LegacyTechLab foi projetado para crescer junto com o desenvolvimento técnico do laboratório.

A evolução planejada é:

```text
Hardware Legado
       ↓
Linux
       ↓
Redes
       ↓
Infraestrutura
       ↓
Cloud
       ↓
Cibersegurança
       ↓
Automação
       ↓
Projetos integrados
```

O mesmo equipamento poderá funcionar como:

- estação Linux;
- cliente SSH;
- servidor de serviços leves;
- estação de administração;
- ambiente de testes;
- laboratório de redes;
- estação para ferramentas Cloud;
- ambiente de estudos de segurança;
- plataforma de automação.

A utilização de cada função dependerá das limitações do hardware e dos requisitos específicos de cada laboratório.

---

# ♻️ Reaproveitamento tecnológico

Um dos princípios do projeto é explorar o potencial de equipamentos que poderiam ser considerados obsoletos para uso cotidiano.

O objetivo não é demonstrar que hardware antigo pode substituir máquinas modernas em qualquer cenário.

O objetivo é demonstrar que:

> **hardware limitado ainda pode possuir valor quando utilizado no contexto adequado.**

Essa abordagem também permite estudar conceitos importantes de infraestrutura:

- ciclo de vida de equipamentos;
- capacidade computacional;
- otimização de recursos;
- sustentabilidade;
- software livre;
- arquitetura;
- dimensionamento;
- troubleshooting.

---

# 💼 Valor para o portfólio

O LegacyTechLab busca demonstrar competências práticas relacionadas à área de **Tecnologia da Informação**, especialmente:

- Linux;
- Infraestrutura de TI;
- Redes;
- Cloud;
- Cibersegurança;
- Hardware;
- Sistemas Operacionais;
- Troubleshooting;
- Automação;
- Documentação técnica.

O diferencial do projeto é que ele parte de uma **limitação real**:

> hardware antigo.

A partir dessa limitação são tomadas decisões técnicas para construir uma plataforma funcional de aprendizagem e experimentação.

O projeto documenta não apenas o resultado, mas também:

**problemas → hipóteses → testes → erros → soluções → aprendizados.**

---

# 🔑 Principais palavras-chave

`Linux` · `IT Infrastructure` · `Infrastructure` · `Networking` · `Cloud Computing` · `Cybersecurity` · `Troubleshooting` · `System Administration` · `Hardware` · `Legacy Hardware` · `Xubuntu` · `Ubuntu` · `Debian` · `Rufus` · `GRUB` · `BIOS` · `MBR` · `Dual Boot` · `TCP/IP` · `DNS` · `DHCP` · `SSH` · `Bash` · `Automation`

---

## 📌 Status do projeto

**🟡 Em desenvolvimento**

> O LegacyTechLab está sendo construído de forma incremental. Novos laboratórios, experimentos, configurações e estudos serão adicionados conforme o ambiente evoluir.

---

## 👨‍💻 Autor

**Diogo Teixeira Pena**

Projeto desenvolvido como parte da construção de um portfólio prático voltado à transição e desenvolvimento profissional em **Tecnologia da Informação**, com foco em **Infraestrutura, Linux, Redes, Cloud e Cibersegurança**.