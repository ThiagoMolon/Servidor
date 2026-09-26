# Como executar o servidor

## Requisitos

- Java 25 instalado (`java -version` deve mostrar a versão 25).
- EULA aceita em `eula.txt` (`eula=true`).
- Os arquivos do servidor e a pasta `mods/` presentes neste diretório.

O servidor usa Minecraft 26.3 com Fabric Loader 0.19.5. O cliente também deve usar Minecraft 26.3 e uma versão compatível do Fabric.

## Iniciar

Abra um terminal e execute:

```bash
cd ~/servidor
java -Xmx2G -jar fabric-server-mc.26.3-loader.0.19.5-launcher.1.1.2.jar nogui
```

Mantenha o terminal aberto enquanto o servidor estiver em uso. A mensagem `Done` indica que ele terminou de iniciar. Não inicie outra cópia apontando para o mesmo mundo.

Para encerrar, digite `stop` no console do servidor e aguarde o salvamento do mundo antes de fechar o terminal.

## Conectar

O `server.properties` atual configura o endereço `xxx.xxx.xxx.xxx` e a porta `yyyyy`. Para conectar por esse endereço, o jogador precisa estar na mesma rede Hamachi e informar:

```text
xxx.xxx.xxx.xxx:yyyyy
```

Com a whitelist ativada, adicione cada conta pelo console do servidor:

```text
whitelist add NOME_DO_JOGADOR
```

Use o nome exato da conta Minecraft. O servidor está com `online-mode=true`, portanto os jogadores precisam autenticar com contas oficiais.

## Problemas comuns

- `session.lock already locked`: outra instância pode estar usando o mundo. Encerre-a com `stop` antes de iniciar novamente; não apague `world/session.lock` enquanto o servidor estiver ativo.
- `You are not white-listed`: confirme o nome com `whitelist list` e adicione-o pelo console.
- Não conecta pela rede: confirme que o servidor está iniciado, que os jogadores estão na mesma rede Hamachi e que estão usando o endereço e a porta acima.
- `UnsupportedClassVersionError`: confira se o Java usado no comando é a versão 25.