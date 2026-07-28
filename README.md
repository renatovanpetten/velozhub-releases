# Veloz Hub — arquivos de atualização

Este repositório existe só para hospedar os **instaladores** do Veloz Hub, que é
o que a atualização automática do app desktop consulta.

**Não há código-fonte aqui.** O código do Veloz Hub é privado.

## Como funciona

O `electron-builder` publica, a cada versão, três arquivos em *Releases*:

| Arquivo | Para que serve |
|---|---|
| `VelozHub_Setup_X.Y.Z.exe` | o instalador |
| `VelozHub_Setup_X.Y.Z.exe.blockmap` | permite baixar só as partes que mudaram |
| `latest.yml` | diz qual é a versão mais nova e o hash do instalador |

O app lê o `latest.yml`, compara com a versão instalada e, se estiver atrás,
baixa e instala sozinho — conferindo o hash antes, para não instalar um arquivo
corrompido ou trocado no caminho.

A instalação é por usuário (AppData), então não pede senha de administrador, e
**nunca apaga os dados** (`deleteAppDataOnUninstall: false`).

## Antes da v2.3.0

Cada versão era um `.exe` enviado na mão, e quem não reinstalava ficava numa
versão antiga usando o mesmo banco de dados — origem de "bug que ninguém
consegue reproduzir". A v2.3.0 é a última instalação manual.
