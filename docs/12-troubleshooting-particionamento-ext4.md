# 12 --- Troubleshooting do Particionamento ext4

## Contexto

Após a criação bem-sucedida da mídia USB e a validação do boot no
Positivo Premium Select 7050, o processo avançou para a instalação do
Xubuntu.

Durante a etapa de particionamento, foi realizada uma tentativa de
criação de uma partição utilizando o sistema de arquivos `ext4`.

## Problema identificado

Foi identificado um problema durante a criação da partição `ext4`.

Neste momento, o projeto registra a ocorrência, mas **não estabelece uma
causa definitiva sem a análise da mensagem/erro exato apresentado pelo
instalador**.

## Estado do troubleshooting

``` text
Mídia USB
    ↓
Boot funcional
    ↓
Instalador do Xubuntu
    ↓
Particionamento
    ↓
Tentativa de criar ext4
    ↓
PROBLEMA IDENTIFICADO
```

## Próximos diagnósticos

A investigação deverá verificar, conforme as evidências disponíveis:

-   mensagem exata apresentada pelo instalador;
-   estrutura atual das partições;
-   espaço livre disponível;
-   unidade selecionada;
-   existência de partições montadas/em uso;
-   compatibilidade entre a configuração planejada e o modo Legacy/MBR;
-   possíveis conflitos com o sistema existente.

## Regra de segurança

Nenhuma alteração destrutiva no armazenamento deve ser realizada
enquanto a causa do problema não estiver suficientemente compreendida.

A prioridade é preservar o Windows e os arquivos pessoais existentes.

## Estado

**Troubleshooting em andamento.**

A instalação do Xubuntu permanece pendente até a resolução e validação
do particionamento.
