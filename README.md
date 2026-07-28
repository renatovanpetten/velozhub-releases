# Veloz Hub — instalação e atualizações

## ⬇️ Baixar a versão mais recente

**[Clique aqui para baixar o Veloz Hub](https://github.com/renatovanpetten/velozhub-releases/releases/latest)**

Na página que abrir, role até **Assets** e clique no arquivo terminado em `.exe`.

> **O Windows vai mostrar um aviso azul** — *"O Windows protegeu o seu PC"*.
> Isso acontece porque o instalador ainda não tem certificado digital (é pago).
> **Não é vírus.** Clique em **Mais informações** → **Executar assim mesmo**.

A instalação é num clique e **não apaga nada**: vendas, clientes, estoque e
ordens de serviço continuam como estão — eles ficam na nuvem, não no
computador. Não precisa desinstalar a versão antiga antes.

---

## A partir da versão 2.3.0, o app se atualiza sozinho

Você não precisa mais baixar nada. O Veloz Hub verifica se saiu versão nova,
baixa e instala sozinho, e reabre quando termina.

**Por que a atualização é obrigatória:** todos os computadores e celulares usam
o mesmo banco de dados. Um aparelho em versão antiga grava dado no formato
errado, e o problema aparece depois — no relatório de outra pessoa, sem
ninguém saber de onde veio. Por isso, quem está atrasado vê uma tela pedindo
para atualizar antes de continuar.

---

## Sobre este repositório

Ele existe só para **hospedar os instaladores**, que é o que a atualização
automática consulta. **Não há código-fonte aqui** — o código do Veloz Hub é
privado.

A cada versão são publicados três arquivos em *Releases*:

| Arquivo | Para que serve |
|---|---|
| `VelozHub_Setup_X.Y.Z.exe` | o instalador |
| `VelozHub_Setup_X.Y.Z.exe.blockmap` | permite baixar só as partes que mudaram |
| `latest.yml` | diz qual é a versão mais nova e o hash do instalador |

O app lê o `latest.yml`, compara com a versão instalada e, se estiver atrás,
baixa e instala — **conferindo o hash antes**, para não instalar um arquivo
corrompido ou trocado no caminho.

A instalação é por usuário (AppData), então não pede senha de administrador, e
nunca apaga os dados (`deleteAppDataOnUninstall: false`).
