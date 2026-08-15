# 11 --- Instalação do Xubuntu

## Estado atual

A instalação do Xubuntu **ainda não foi concluída**, mas o diagnóstico
do problema de particionamento já está fechado.

## Etapas concluídas

-   [x] Hardware identificado
-   [x] Modo de boot identificado
-   [x] Estrutura de armazenamento analisada
-   [x] Distribuição Linux escolhida
-   [x] Mídia USB criada
-   [x] Boot pelo USB validado
-   [x] Processo de instalação iniciado
-   [x] Etapa de particionamento alcançada
-   [x] Partição `ext4` (`sda4`, 80,53 GB) criada com sucesso (via
    GParted, já que o particionador do Subiquity não conseguia criá-la
    diretamente)
-   [x] Causa raiz do erro de associação do ponto de montagem
    identificada
-   [x] Contorno funcional confirmado (tamanho em Bytes exatos)
-   [x] Rota alternativa adotada: instalação manual via `debootstrap`
    + `chroot` (ver `13-instalacao-manual-debootstrap.md`)
-   [x] Sistema base, kernel e `xubuntu-desktop` instalados
-   [x] `grub-install` executado com sucesso (i386-pc / Legacy)
-   [x] GRUB configurado com entrada manual para o Windows (ver
    `14-boot-real-e-validacao.md`)
-   [x] Boot real testado --- menu do GRUB funcional com as duas
    entradas (foto real)
-   [x] Login funcional (modo texto e gráfico via LightDM, foto real)
-   [ ] `/etc/fstab` preenchido em definitivo --- relatado no `.txt`
    de 14/08, ainda sem foto correspondente
-   [ ] Hostname/`/etc/hosts` corrigidos em definitivo --- relatado no
    `.txt` de 14/08, ainda sem foto correspondente
-   [ ] Validação final pós-reboot com tudo corrigido, com evidência
    fotográfica

## Histórico do problema de particionamento

Foram identificados três erros distintos do instalador Subiquity ao
longo da investigação, todos relacionados ao cálculo de tamanho da
partição:

1. `ValueError: new partition too large` (criação direta pelo
   instalador)
2. `Exception: Exceeded number of available partitions` (limite de 4
   partições primárias em MBR)
3. `Exception: partition size too large` (ao tentar associar o ponto
   de montagem `/` a uma partição já existente)

O detalhamento completo, incluindo a causa raiz e o contorno
encontrado, está em `12-troubleshooting-particionamento-ext4.md`.

## Próxima etapa

O projeto seguiu pela rota manual (`debootstrap`), documentada em
`13-instalacao-manual-debootstrap.md` e `14-boot-real-e-validacao.md`.
O boot real e o dual boot já foram comprovados por foto. Falta apenas:

1.  Anexar evidência fotográfica da correção definitiva de
    `/etc/fstab` (já relatada em texto, ainda sem foto);
2.  Anexar evidência fotográfica da correção definitiva de
    `/etc/hosts`/hostname (já relatada em texto, ainda sem foto);
3.  Anexar evidência da validação final pós-reboot (`getent hosts`,
    `mount -a`, reboot limpo);
4.  Só então marcar a instalação como definitivamente concluída.

## Observação

Este documento registra o estado real do processo. A instalação **não
deve ser considerada concluída** até que o sistema seja instalado e
validado no equipamento.
