# 10 --- Troubleshooting do GRUB

## Ocorrência

Durante a preparação da mídia USB, o Rufus apresentou:

``` text
Esta imagem usa o Grub 2.12, mas este aplicativo inclui somente os arquivos de instalação para Grub 2.14.
```

Evidência:

``` text
../screenshots/rufus/01-grub-version-warning.png
```

## Contexto do equipamento

O equipamento foi identificado com:

``` text
Boot: Legacy / BIOS
Tabela: DOS / MBR
```

Essas informações foram consideradas durante a análise da mídia e do
processo de boot.

## Validação

Apesar do aviso apresentado pelo Rufus, a mídia USB acabou sendo criada
com sucesso.

O notebook conseguiu realizar boot pelo USB.

Isso permitiu concluir que o aviso não impediu a inicialização da mídia
no equipamento.

## Conclusão

O evento relacionado ao GRUB permanece registrado como parte do
troubleshooting, mas **não há evidência suficiente para afirmar que ele
representava uma falha definitiva do processo**.

A investigação do GRUB poderá ser retomada caso surjam problemas durante
a instalação ou configuração do bootloader.

## Estado

``` text
Aviso GRUB
    ↓
Mídia criada
    ↓
Boot pelo USB
    ↓
Funcionamento confirmado
```

O foco atual do troubleshooting é outro: o problema encontrado durante a
criação da partição `ext4`.
