<p align="center">
  <img src="assets/banner.svg" alt="Granny: Legacy Speedrun Mod" width="100%">
</p>

# Granny: Legacy Speedrun Mod

[English](README.md) | [Русский](README.ru.md) | [Português](README.pt.md)

[![Release](https://img.shields.io/github/v/release/T300850/GrannyLegacySpeedrunMod?display_name=tag&sort=semver)](https://github.com/T300850/GrannyLegacySpeedrunMod/releases)
[![Game](https://img.shields.io/badge/game-Granny%3A%20Legacy-1f1f1f)](https://store.steampowered.com/search/?term=Granny+Legacy)
[![MelonLoader](https://img.shields.io/badge/MelonLoader-0.7.x-5c2d91)](https://melonwiki.xyz/)

**Cronômetro, splits, controle de seed, mira personalizada, som de morte e anti-cheat para Granny: Legacy.**

Feito por [TL12 Mods](https://t.me/TL12Mods) · [speedrun.com](https://www.speedrun.com/users/t300850) · [GitHub](https://github.com/T300850)

> **Baixar:** [GitHub Releases](https://github.com/T300850/GrannyLegacySpeedrunMod/releases) · **Changelog:** [CHANGELOG.md](CHANGELOG.md)

---

## Recursos

- **Cronômetro e splits** — timer automático, melhor tempo, comparação com PB, overlay de splits e tela de resultados separada.
- **Controle de seed** — definir seed, salvar seeds favoritas, marcar seeds como Extras, usar a seed atual e copiar a seed usada pelo jogo.
- **Pontos de spawn** — escolher e memorizar pontos da Granny/Grandpa separadamente para cada versão do jogo.
- **Mira** — colorir o ponto nativo do jogo, mira em cruz/círculo personalizada, cor e tamanho.
- **Som de morte personalizado** — WAV, MP3, OGG e AIFF, com botão de teste e cooldown por tentativa.
- **Splits do Playhouse** — splits automáticos para o quebra-cabeça das engrenagens.
- **Splits de arame/corrente por versão** — 1.0–1.1 (2 arames), 1.2–1.7 (3 arames), 1.8+ (4 etapas, incluindo o alicate de corrente).
- **Anti-cheat** — detecta entrada sintética, autoclickers, macros, manipulação de velocidade/tempo, distância de coleta e alcance das mãos. Gera um relatório local e mostra um aviso.
- **Visual e desempenho** — alternar pós-processamento, limite de FPS, limitador experimental de 5–15 FPS e overlay de teclas.
- **Qualidade de vida** — pular a cutscene de acordar, trocar os botões laterais do mouse, reinício rápido, atalho para o menu, copiar resultados.
- **Idiomas** — russo, inglês e português (RU / EN / PT).

O mod foi testado nas versões **1.7.9** e **1.8.8** do jogo.

---

## Requisitos

- Windows com **Granny: Legacy**.
- **MelonLoader 0.7.x** (recomendado 0.7.3 ou mais recente).
- Para o som de morte: bibliotecas **NAudio** e **NVorbis** na pasta `UserLibs`.

---

## Instalação

1. Instale o **MelonLoader** na pasta do jogo e abra o jogo uma vez para que ele crie as pastas necessárias.
2. Baixe o arquivo da release mais recente. Ele já contém as pastas `Mods` e `UserLibs` com os arquivos corretos.
3. Copie `GrannyLegacySpeedrunMod.dll` para:

   ```text
   Granny_Legacy/Mods/
   ```

4. Copie **todos** os arquivos `NAudio*.dll` e `NVorbis*.dll` para:

   ```text
   Granny_Legacy/UserLibs/
   ```

   Isso é necessário para o som de morte personalizado. Copie todos os `NAudio*.dll` do arquivo de release, não apenas `NAudio.dll`.

5. Abra o jogo. O menu do mod abre com **F2**.

Estrutura final:

```text
Granny_Legacy/
├─ Mods/
│  └─ GrannyLegacySpeedrunMod.dll
├─ UserLibs/
│  ├─ NAudio.dll
│  ├─ NAudio.Asio.dll
│  ├─ NAudio.Core.dll
│  ├─ NAudio.Midi.dll
│  ├─ NAudio.Vorbis.dll
│  ├─ NAudio.Wasapi.dll
│  ├─ NAudio.WinMM.dll
│  └─ NVorbis.dll
└─ UserData/
   ├─ GrannyLegacySpeedrunMod_Config.txt
   └─ GrannyLegacySpeedrunMod_AntiCheat.txt
```

> A pasta `UserData` é criada após a primeira execução. O jogo e o MelonLoader precisam de permissão de escrita nas próprias pastas; evite instalar em diretórios protegidos do sistema.

---

## Controles

| Tecla | Ação |
| --- | --- |
| **F2** | Abrir/fechar as configurações do mod (sempre funciona) |
| **F1** | Abrir/fechar o overlay de debug |
| **F5** | Reiniciar a run atual (padrão; pode ser alterado) |
| `menuKey` | Abrir o overlay do mod (desativado por padrão) |
| `exitKey` | Voltar ao menu principal (desativado por padrão) |
| `experimentalFpsKey` | Alternar o FPS experimental (padrão `F4`) |

Os atalhos são configurados na aba **Main**. O menu sempre abre com **F2**, mesmo que o atalho do overlay esteja em `None`.

Teclas úteis com o overlay de debug aberto: **L** alterna os logs do mod, **C** copia os últimos resultados.

---

## Som de morte

1. Abra **F2 → Visuals**.
2. Clique em **Choose file...** e escolha um arquivo `.wav`, `.mp3`, `.ogg`, `.aiff` ou `.aif`.
3. Aguarde a linha de status verde: o arquivo é decodificado em segundo plano.
4. Clique em **Test** para ouvir.
5. Durante a run, o som toca quando o jogador morre. Há um cooldown para os sons não se sobreporem.

Se o status ficar vermelho ou o botão de teste não fizer nada:

- confira se **todos** os `NAudio*.dll` e `NVorbis*.dll` estão em `UserLibs`;
- veja o erro exato em `MelonLoader/Latest.log`;
- teste um WAV curto para descartar problema de codec.

O restante do mod funciona sem o NAudio; apenas o som de morte personalizado depende dele.

---

## Seeds

- A aba **Seeds** permite digitar uma seed, aplicar, salvar e marcar como Extras.
- **Random** aplica uma seed aleatória.
- A seed exibida nos resultados/estatísticas é a seed usada pelo jogo. Se o jogo não a expõe, o mod usa `PlayerPrefs.GameSeed` como fallback.
- A lista de seeds fica em `UserData/GrannyLegacySpeedrunMod_Seeds.txt` (ou no arquivo configurado pelo mod).
- Salve as seeds antes de trocar a versão do jogo ou reinstalar.

---

## Anti-cheat

O anti-cheat roda localmente e **não envia dados pela rede**.

Ele verifica:

- entrada sintética (`SendInput`) e ferramentas de injeção de entrada;
- autoclickers e sequências de cliques muito rápidas;
- macros repetitivas;
- mudanças de velocidade/time scale;
- distância suspeita ao coletar itens;
- alcance das mãos acima do normal.

A entrada sintética só é verificada quando a janela do jogo está em primeiro plano. Teclas de volume, mídia e navegador, além de eventos injetados isolados, são ignorados para evitar falsos positivos.

O relatório local é gravado em:

```text
Granny_Legacy/UserData/GrannyLegacySpeedrunMod_AntiCheat.txt
```

A aba **Anti-cheat** mostra as ocorrências atuais e tem um botão de limpar. Falsos positivos podem acontecer com ferramentas de acessibilidade, macros, acesso remoto e automação; limpe antes da run se você não está trapaceando.

### Filtro de logs

No overlay de debug (**F1**), o botão **Logs** alterna entre:

- **Logs: all** — todos os logs normais do mod;
- **Logs: SUS only** — esconde mensagens rotineiras, mas mantém avisos de suspeita e cheat do anti-cheat.

A opção é salva como `hideMelonLogs` no arquivo de configuração.

---

## Configuração

Arquivo de configuração:

```text
Granny_Legacy/UserData/GrannyLegacySpeedrunMod_Config.txt
```

Chaves principais:

```ini
restartKey=F5
menuKey=None
exitKey=None
experimentalFpsKey=F4
language=pt
hideMelonLogs=0
```

- `language` aceita `ru`, `en` ou `pt`.
- Use `None` para desativar um atalho.
- Se apagar o arquivo, as configurações padrão serão recriadas; alguns dados em PlayerPrefs (tema, histórico de seeds etc.) podem permanecer.

---

## Limitador de FPS experimental

A opção **Experimental FPS (5–15)** é para testes e runs cinematográficas. Ela altera o timing dos frames e **não deve ser usada em runs oficiais**, a menos que as regras da comunidade permitam explicitamente. O limite normal de FPS (30–240 / ilimitado) é seguro para uso comum.

---

## Código-fonte

O código-fonte é privado para proteger as assinaturas do anti-cheat. Builds oficiais são publicados em [Releases](https://github.com/T300850/GrannyLegacySpeedrunMod/releases).

---

## Solução de problemas

**O mod não carrega.**  
Verifique se o MelonLoader está instalado para o executável correto e abra `MelonLoader/Latest.log`. O log deve mostrar `GrannyLegacySpeedrunMod` na lista de mods carregados.

**F2 não faz nada.**  
Foque a janela do jogo. F2 é fixo e não depende do atalho do overlay.

**O botão do som de morte não faz nada.**  
Coloque todos os DLLs do NAudio/NVorbis em `UserLibs` e reinicie o jogo. Confira a linha de status e o `Latest.log`.

**A mira nativa continua branca.**  
Selecione **Crosshair → Game** e uma cor diferente de branco. Na 1.7.9 o jogo reescreve a cor da mira nativa no próprio `Update`; o mod reaplica a cor a cada frame. Se ainda falhar, veja a linha de diagnóstico da mira no log.

**A seed nos resultados está errada.**  
Inicie a run depois de aplicar a seed e confira as linhas `[seed]` no `Latest.log`. O mod captura a seed após `GeneratePlacement` e usa `PlayerPrefs.GameSeed` quando o jogo retorna zero.

**O anti-cheat mostra SUS depois de acesso remoto ou macro.**  
Limpe as ocorrências antes da run. Entrada sintética de automação é marcada de propósito.

---

## Créditos

- **TL12 Mods** — autor do mod.
- **MelonLoader** e **Harmony** — carregamento e patches.
- **NAudio** e **NVorbis** — decodificação de áudio.
- Comunidade de speedrun de Granny: Legacy — testes, rotas e feedback.

---

## Aviso

Este é um mod de fã não oficial. Não é afiliado à DVloper nem aos desenvolvedores de Granny: Legacy. Use por sua conta e risco, faça backup dos saves e confira as regras atuais da comunidade antes de enviar uma run.
