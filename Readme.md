# LegacyTechLab — Transformando Hardware Legado em um Laboratório de TI

O **LegacyTechLab** transforma um notebook Positivo Premium Select 7050 em um laboratório prático para estudos de Linux, Redes, Infraestrutura, Cloud, Cibersegurança e automação.

O projeto documenta não apenas o resultado final, mas também os problemas encontrados, as hipóteses investigadas, as soluções aplicadas e as validações realizadas.

## 🎯 Objetivos

- Reaproveitar hardware legado como laboratório de TI.
- Praticar administração Linux e troubleshooting.
- Construir uma base para estudos de Redes, Infraestrutura, Cloud e Cibersegurança.
- Registrar decisões técnicas e evidências de forma reproduzível.
- Transformar limitações reais de hardware em oportunidades de aprendizagem.

## 🖥️ Hardware

| Componente | Especificação |
|---|---|
| Equipamento | Positivo Premium Select 7050 |
| CPU | Intel Core i3 M350 — 1ª geração |
| RAM | 8 GB DDR3 |
| SSD principal | ~240 GB — `/dev/sda` |
| HDD secundário | ~320 GB — `/dev/sdb` |
| Tabela de partições | DOS/MBR |
| Modo de boot | Legacy/BIOS |

### Estrutura final do SSD

```text
/dev/sda
├── sda1 — NTFS — Windows Boot
├── sda2 — NTFS — Windows
├── sda3 — NTFS — Recovery
└── sda4 — ext4 — Xubuntu
```

## 🐧 Sistema final

- **Xubuntu 24.04.4 LTS**
- **Kernel 6.8.0-31-generic**
- `/dev/sda4` — ext4
- UUID: `e7b99872-a6bc-4efa-bb18-72cbf0993369`
- GRUB `i386-pc`
- Dual boot Windows + Xubuntu

## 🧭 Evolução do projeto

```text
Hardware legado
      ↓
Diagnóstico
      ↓
Preparação do Windows
      ↓
Criação da mídia USB
      ↓
Problemas de boot
      ↓
Problemas de particionamento
      ↓
Troubleshooting do Subiquity
      ↓
GParted e validação do armazenamento
      ↓
Instalação manual com debootstrap + chroot
      ↓
Kernel + initramfs + Xubuntu Desktop
      ↓
GRUB
      ↓
Entrada manual do Windows
      ↓
fstab + hostname + hosts
      ↓
Validação final
      ↓
🟢 LABORATÓRIO FUNCIONAL
```

## ⚙️ Problemas encontrados e soluções

### 1. Rufus e mídia de instalação

Durante a preparação da mídia foram observadas mensagens relacionadas a DBX/Secure Boot, versão do GRUB e o erro `0xC0030003`.

As evidências do Rufus estão organizadas em:

```text
screenshots/Rufus/
```

### 2. Problema de particionamento

O Subiquity apresentou:

```text
ValueError: new partition too large
```

Foram comparados valores apresentados pelo instalador e pelas ferramentas de particionamento, considerando GB, GiB, MB, MiB e bytes.

Foram utilizados:

```text
fdisk
parted
lsblk
blkid
GParted
```

### 3. Instalação manual

Após as dificuldades do instalador gráfico, a instalação foi concluída manualmente utilizando:

```text
debootstrap
chroot
kernel
initramfs
xubuntu-desktop
```

### 4. GRUB e Windows

O `os-prober` estava instalado, mas não criou automaticamente a entrada do Windows.

Foi criada uma entrada manual:

```text
menuentry "Windows" {
    insmod part_msdos
    insmod ntfs
    insmod chain
    set root=(hd0,msdos1)
    chainloader +1
}
```

### 5. Sistema inicialmente montado como somente leitura

Durante o primeiro boot, `/dev/sda4` foi montada como `ro`.

A investigação identificou que `/etc/fstab` ainda continha:

```text
# UNCONFIGURED FSTAB FOR BASE SYSTEM
```

Foi então configurada a montagem persistente:

```text
UUID=e7b99872-a6bc-4efa-bb18-72cbf0993369 / ext4 defaults 0 1
```

Após a correção, a raiz passou a ser validada como:

```text
/dev/sda4 ext4 rw,relatime
```

### 6. Hostname e `/etc/hosts`

Também foi corrigido o arquivo `/etc/hosts`, incluindo:

```text
127.0.0.1 localhost
127.0.1.1 xubuntu
```

A resolução do hostname foi posteriormente validada com `getent`.

## 🧪 Validação final

### Boot

- ✅ GRUB
- ✅ Windows
- ✅ Xubuntu
- ✅ Reboot

### Sistema Linux

- ✅ Login do usuário `diogo`
- ✅ `/dev/sda4` em `rw`
- ✅ `/etc/fstab` configurado
- ✅ `/etc/hosts` corrigido
- ✅ Hostname resolvido
- ✅ Ambiente gráfico Xubuntu
- ✅ LightDM

### Resultado

**Windows + Xubuntu funcionando em dual boot.**

## 🛠️ Destaques técnicos

- Diagnóstico de `ValueError: new partition too large`.
- Troubleshooting de particionamento.
- Comparação de GB/GiB/MB/MiB/bytes.
- Uso de `fdisk`, `parted`, `lsblk`, `blkid` e GParted.
- Instalação manual via `debootstrap`.
- Administração de `chroot`.
- Instalação e validação de kernel e initramfs.
- Instalação do Xubuntu Desktop.
- Instalação do GRUB `i386-pc`.
- Investigação do `os-prober`.
- Criação de entrada manual de boot do Windows.
- Configuração de `/etc/fstab`.
- Configuração de hostname e `/etc/hosts`.
- Validação pós-reboot.

## 📚 Documentação

A pasta `docs/` contém a documentação detalhada das etapas do laboratório, incluindo:

- contexto e objetivos;
- hardware;
- avaliação do equipamento;
- escolha do Xubuntu;
- planejamento do dual boot;
- boot;
- Rufus;
- particionamento;
- troubleshooting;
- instalação manual;
- GRUB;
- configuração do Xubuntu;
- validação;
- lições aprendidas.

## 📸 Evidências

As evidências visuais estão organizadas por etapa:

```text
screenshots/
├── Rufus/
├── BIOS/
├── Boot/
├── Partitioning/
├── Troubleshooting/
├── Installation/
├── Manual-Install/
└── Validation/
```

Capturas intermediárias ou repetitivas não foram eliminadas. Elas permanecem separadas em:

```text
screenshots/Archive-Redundantes/
```

Essa separação permite manter o histórico completo sem sobrecarregar a documentação principal.

Os logs técnicos utilizados durante o projeto também foram preservados no repositório.

## 🧠 Lições aprendidas

O projeto demonstrou que a instalação de um sistema operacional em hardware legado pode exigir mais do que seguir o fluxo de uma ferramenta gráfica.

Os principais aprendizados foram:

1. Validar resultados de ferramentas automatizadas.
2. Interpretar corretamente unidades de armazenamento.
3. Trabalhar com ferramentas de baixo nível quando necessário.
4. Utilizar evidências para conduzir o troubleshooting.
5. Diferenciar hipótese, teste, resultado e solução.
6. Utilizar linha de comando para recuperar ou concluir uma instalação.
7. Documentar problemas, e não apenas o resultado final.

## 🔭 Próximas etapas

Com a base Linux funcional, o LegacyTechLab poderá evoluir para:

- Redes e serviços Linux;
- administração de servidores;
- monitoramento;
- virtualização e containers;
- automação;
- fundamentos de Cloud;
- práticas de Cibersegurança;
- testes de infraestrutura;
- projetos de troubleshooting e documentação.

## 📌 Princípio do projeto

> **Diagnosticar → Planejar → Implementar → Testar → Documentar → Evoluir**

O objetivo não é apenas fazer o equipamento funcionar, mas transformar cada problema encontrado em uma oportunidade de aprendizagem técnica.

## 👤 Autor

**Diogo Teixeira Pena**

Projeto desenvolvido como laboratório prático para evolução profissional em **Tecnologia da Informação, Infraestrutura, Linux, Cloud e Cibersegurança**.
