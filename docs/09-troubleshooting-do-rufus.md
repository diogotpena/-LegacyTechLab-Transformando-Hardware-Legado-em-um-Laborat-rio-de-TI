# 09 --- Troubleshooting do Rufus

## Objetivo

Registrar os problemas encontrados durante a criação da mídia USB e o
processo de validação até a obtenção de uma mídia funcional.

## Ocorrência 1 --- Aviso relacionado ao GRUB

O Rufus apresentou a mensagem:

``` text
Esta imagem usa o Grub 2.12, mas este aplicativo inclui somente os arquivos de instalação para Grub 2.14.
```

Evidência:

``` text
../screenshots/rufus/01-grub-version-warning.png
```

## Ocorrência 2 --- Erro de criação

Também foi registrado:

``` text
Erro: [0xC0030003]
```

e:

``` text
unable to create file [0x00000003]
```

Evidência:

``` text
../screenshots/rufus/02-error-0xC0030003.png
```

O log bruto está em:

``` text
../logs/rufus/rufus-error.log
```

## Resultado

Após as tentativas de troubleshooting, a mídia foi criada com sucesso.

O teste mais importante foi realizado no equipamento de destino:

> O Positivo Premium Select 7050 conseguiu iniciar pelo USB.

## Conclusão

O problema de criação da mídia USB foi superado.

A mensagem relacionada ao GRUB e o erro `0xC0030003` permanecem
documentados como parte do histórico do projeto, mas não impediram a
utilização da mídia.

## Aprendizado

O processo reforçou a importância de:

-   registrar erros;
-   preservar logs;
-   manter evidências visuais;
-   testar a mídia no equipamento real;
-   separar problemas de criação da mídia de problemas de instalação.

## Estado

O troubleshooting do Rufus está concluído para a etapa atual.

O foco do projeto avançou para o particionamento e instalação do
Xubuntu.
