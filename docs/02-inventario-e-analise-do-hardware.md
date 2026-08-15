# 02 --- Inventário e Análise do Hardware

## Equipamento

| Componente | Informação |
|---|---|
| Notebook | Positivo Premium Select 7050 |
| Processador | Intel Core i3 M350 (1ª geração) |
| Memória RAM | 8 GB DDR3 |
| SSD | ~240,06 GB — modelo **walram 240G** (`/dev/sda`) |
| HD adicional | ~320,07 GB — modelo **FUJITSU MJA2320BH G2** (`/dev/sdb`), usado para arquivos pessoais |
| Touchpad | Inoperante — navegação feita via teclado durante a instalação |

Os modelos de SSD e HD foram confirmados via GNOME Disks e pelos
comandos `fdisk -l` / `parted print free` (evidência:
`screenshots/system/01-gnome-disks-walram-240g-layout.png`).

## Objetivo da análise

Antes da instalação do Linux, foi necessário identificar os recursos
disponíveis e as limitações do equipamento.

## Avaliação inicial

O equipamento possui hardware antigo, mas os 8 GB de RAM e o SSD tornam
possível utilizá-lo como uma plataforma de laboratório para cargas de
trabalho leves e estudos de administração de sistemas.

## Limitações esperadas

-   Processador de primeira geração;
-   menor capacidade de processamento em comparação com hardware atual;
-   limitações para virtualização e serviços pesados;
-   necessidade de utilizar software compatível com o desempenho
    disponível;
-   touchpad inoperante — dependência de teclado ou mouse externo.

## Oportunidade de aprendizado

As limitações do hardware fazem parte do próprio laboratório. O projeto
permite estudar como dimensionar software e serviços de acordo com os
recursos disponíveis.

## Evidências visuais

### Inventário visual do armazenamento

![Inventário visual do armazenamento](../screenshots/system/01-gnome-disks-walram-240g-layout.png)

### Inventário das partições

![Inventário das partições](../screenshots/system/05-efibootmgr-lsblk-full-output.png)

