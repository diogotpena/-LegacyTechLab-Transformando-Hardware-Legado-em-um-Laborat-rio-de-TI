# 08 --- Criação da Mídia USB

## Objetivo

Criar uma mídia USB inicializável para instalar e testar o Xubuntu 24.04
no Positivo Premium Select 7050.

## Ferramenta

Foi utilizado o Rufus para preparação da mídia.

## Problemas iniciais

Durante as primeiras tentativas, foram observadas mensagens relacionadas
ao GRUB e ocorreu um erro durante a criação da mídia.

As evidências estão organizadas em:

``` text
../screenshots/rufus/
```

e o log disponível está em:

``` text
../logs/rufus/rufus-error.log
```

## Resultado

Após o troubleshooting, a mídia USB foi criada com sucesso.

O resultado foi validado no equipamento físico: **o Positivo Premium
Select 7050 conseguiu realizar boot pelo USB**.

## Estado atual

``` text
ISO Xubuntu 24.04
        ↓
Rufus
        ↓
Mídia USB criada
        ↓
Boot no notebook
        ↓
SUCESSO
```

A mídia funcional permitiu avançar para a etapa de instalação e
particionamento.

## Próxima etapa

O próximo desafio técnico passou a ser a criação e configuração das
partições necessárias para o Xubuntu.
