# 07 --- Diagnóstico de Boot e Armazenamento

## Modo de boot

Foi identificado que o equipamento utiliza:

``` text
BIOS: Legacy / Herdado
```

## Tabela de partição

Também foi identificado:

``` text
Disklabel type: dos
```

Esse resultado é compatível com uma tabela de partição DOS/MBR.

## Capacidade observada

Durante o diagnóstico foram registrados aproximadamente:

``` text
Espaço utilizado: 53,8 GB
Espaço livre:     168 GB
Capacidade:       222 GB
```

## Evidência visual

O diagnóstico do armazenamento possui uma evidência visual em:

``` text
../screenshots/system/disks-partition-layout.png
```

## Troubleshooting

Durante o processo de diagnóstico também ocorreu uma mensagem
relacionada à utilização do `fdisk`:

``` text
fdisk: invalid option -- '1'
Try 'fdisk --help' for more information.
```

O evento foi tratado inicialmente como possível questão de sintaxe/opção
do comando, e não como evidência de defeito físico do armazenamento.

## Importância para a instalação

As informações de boot e particionamento são fundamentais para evitar
alterações incorretas no armazenamento durante a instalação do Xubuntu.

O problema posteriormente identificado na criação da partição `ext4`
será documentado separadamente.
