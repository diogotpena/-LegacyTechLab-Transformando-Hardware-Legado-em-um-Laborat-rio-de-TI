# 06 --- Planejamento do Dual Boot

## Objetivo

Avaliar a possibilidade de instalar o Xubuntu mantendo o sistema Windows
existente.

## Premissa

Antes de qualquer alteração no armazenamento, é necessário confirmar:

-   qual unidade contém o Windows;
-   qual unidade corresponde ao SSD;
-   qual unidade corresponde ao HD de arquivos pessoais;
-   estrutura atual das partições;
-   espaço disponível;
-   modo de inicialização utilizado pelo equipamento.

## Ambiente identificado

O notebook utiliza:

``` text
Boot: Legacy / BIOS
Tabela de partição: DOS / MBR
```

## Estratégia

A instalação deve priorizar a preservação dos dados existentes.

O fluxo planejado é:

``` text
Diagnóstico
    ↓
Identificação das unidades
    ↓
Análise das partições
    ↓
Definição do espaço para Linux
    ↓
Criação das partições
    ↓
Instalação
    ↓
Validação do boot
```

## Estado atual

O processo já chegou à etapa de particionamento do instalador do
Xubuntu.

Durante uma tentativa de criação da partição `ext4`, foi identificado um
problema que passou a ser o foco atual do troubleshooting.

A instalação definitiva ainda não foi concluída.
