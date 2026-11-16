# 🕹️ Adventure Retrô por IA

**Adventure Retrô por IA** é um motor de jogos de aventura em texto (*Text Adventure*) movido por Inteligência Artificial, projetado para recriar a atmosfera mágica, desafiadora e nostálgica dos clássicos jogos de microcomputadores da década de 1980.

Através de um *System Prompt* cuidadosamente engenheirado, qualquer modelo de linguagem moderno (como Gemini, ChatGPT, Claude, entre outros) se transforma em um narrador e motor gráfico baseado em caracteres, gerando cenários dinâmicos em **Arte ASCII enriquecida com blocos semigráficos e emojis**, quebra-cabeças lógicos e exploração livre.

## 💾 Inspiração Histórica

Este projeto nasceu da nostalgia pelos jogos de *adventure* que rodavam no saudoso microcomputador brasileiro **CP400** (fabricado pela Prologica nos anos 80, compatível com a linha TRS-80 Color Computer).

Naquela época, sem gráficos realistas ou trilhas sonoras complexas, a imaginação do jogador era o verdadeiro motor gráfico. Jogos como *Calixto Island*, *The Black Sanctum*, *Sea Quest* e clássicos da *Scott Adams* desafiavam o jogador a observar atentamente o cenário, desenhar mapas em folhas de papel quadriculado e descobrir os comandos exatos de duas palavras (`VERBO + SUBSTANTIVO`) para superar obstáculos.

O **Adventure Retrô por IA** resgata essa essência pura de descoberta e raciocínio lógico, adicionando uma camada visual híbrida que une caracteres ASCII tradicionais, blocos semigráficos de 8 bits e emojis modernos.

## 🚀 Como Iniciar o Jogo

Você não precisa instalar nenhum compilador, emulador ou dependência. Basta utilizar qualquer interface de chat com Inteligência Artificial:

1. Acesse o arquivo [**`PROMPT.md`**](./PROMPT.md) neste repositório.
2. Copie todo o conteúdo do prompt (a partir da seção de instruções do sistema).
3. Abra uma **nova conversa** na sua IA favorita (recomendamos modelos com boa capacidade de raciocínio e seguimento de instruções).
4. Cole o prompt e envie.
5. **Calibração de Tela e Tema:** Na primeira tela, o jogo exibirá uma régua numerada de `1` a `80`. Informe à IA:
   * O **maior número visível** na sua tela sem precisar usar a barra de rolagem horizontal (ideal para jogar tanto no celular quanto no computador).
   * O **tema** que você deseja jogar (ex: *Mansão Assombrada*, *Estação Espacial*, *Masmorra Medieval*, ou qualquer ideia original sua).

> **💡 Nota de Compatibilidade:** Embora este prompt tenha sido projetado com a intenção de funcionar em todas as IAs generativas modernas, até o momento ele **foi testado e homologado apenas no Google Gemini**.

## 🎮 Como Jogar e Mecânicas

Diferente dos jogos modernos que entregam todas as respostas na tela, aqui **você precisa investigar o ambiente**:

* **Estética Fiel ao CP400 (Padrão MC6847 e Tela Dividida):** Todo o texto do jogo é exibido sem acentos ou cedilha (simulando o gerador de caracteres ASCII de 7 bits do CP400) e com descrições telegráficas enxutas, organizadas no clássico formato *Split-Screen* (*Scott Adams*): janela do cenário + `ITENS VISIVEIS` + `SAIDAS OBVIAS` no topo, separados por uma linha divisória com o feedback do interpretador BASIC logo abaixo.
* **Mapas Consistentes (Matriz de 20 a 30 Salas):** Cada aventura gerada possui entre **20 e 30 salas** mapeadas internamente em coordenadas cartesianas fixas (como uma matriz `DIM` no Color BASIC), garantindo que os caminhos de ida e volta (`NORTE` ↔ `SUL`, `LESTE` ↔ `OESTE`) sejam 100% simétricos e permitindo desenhar mapas reais no papel.
* **Sem Comandos Prontos na Tela:** A descrição do cenário apresenta apenas o ambiente, os objetos visíveis e as saídas disponíveis. Cabe a você deduzir quais ações tomar.
* **Objetos Dinâmicos no Cenário:** Todo item que pode ser coletado aparece desenhado (com seu respectivo emoji ou símbolo) dentro da arte ASCII da sala. Quando você pega o item, ele desaparece da ilustração do cenário e da lista de itens visíveis.
* **Inventário Limitado (Máximo de 6 Itens):** Você só pode carregar até **6 itens** simultaneamente. Para resolver certos enigmas, será necessário gerenciar sua mochila e deixar itens em salas estratégicas para buscá-los depois.
* **Combinação de Itens:** Alguns desafios exigem unir dois itens diferentes (encontrados na mesma sala ou em salas distintas) para criar uma nova ferramenta ou objeto. Quando dois itens são combinados, o novo item passa a ocupar apenas **1 espaço** no inventário.
* **Descarte e Persistência:** Ao soltar um item em qualquer sala, ele sai do seu inventário e passa a aparecer desenhado no cenário daquela sala, permanecendo lá até que você volte para pegá-lo.
* **Escuridão e Fonte de Luz:** Assim como nos clássicos dos anos 80, áreas escuras exigem uma fonte de luz ativa (lanterna com pilhas, tocha acesa, lampião). Avançar às cegas na escuridão sem iluminar o ambiente pode levar a armadilhas fatais e ao clássico *Game Over*!

## ⌨️ Exemplos de Comandos

O sistema reconhece comandos curtos e diretos no estilo clássico (`VERBO` ou `VERBO + SUBSTANTIVO`), sem necessidade de acentuação:

| Categoria | Exemplos de Comandos | O que faz |
| :--- | :--- | :--- |
| **Movimentação** | `NORTE`, `SUL`, `LESTE`, `OESTE` (ou `N`, `S`, `L`, `O`), `SUBIR`, `DESCER` | Move o personagem para as saídas disponíveis no cenário. |
| **Observação** | `OLHAR`, `EXAMINAR MESA`, `LER BILHETE` | Descreve novamente a sala ou inspeciona um objeto em detalhe. |
| **Manipulação** | `PEGAR CHAVE`, `LARGAR LANTERNA`, `DEIXAR CORDA` | Coleta um item visível na sala ou solta um item do inventário no chão. |
| **Combinação** | `COMBINAR CORDA GANCHO`, `UNIR PILHA LANTERNA` | Une dois itens do inventário para formar um novo item (ocupa 1 espaço). |
| **Interação** | `ABRIR PORTA`, `USAR CHAVE`, `ACENDER TOCHA`, `EMPURRAR ESTATUA` | Interage com elementos do cenário ou utiliza itens carregados. |
| **Sistema** | `INVENTARIO` (ou `I`), `PONTOS` (ou `SCORE`), `AJUDA`, `REINICIAR AVENTURA` | Lista os itens carregados, consulta a pontuação (0 a 100), pede dicas ou reinicia o jogo. |

## 🖥️ Exemplos de Telas do Jogo (Modo 80 Colunas)

### 1. Tela de Boot e Calibração de Largura

Logo ao iniciar o prompt, o jogo calibra o tamanho do quadro negro para o seu dispositivo:

```text
12345678901234567890123456789012345678901234567890123456789012345678901234567890
        10        20        30        40        50        60        70        80

╔════════════════════════════════╗
║   🕹️  ADVENTURE RETRO  👾      ║
║   MOTOR DE AVENTURA 8-BITS     ║
╚════════════════════════════════╝

OBSERVE A REGUA ACIMA. QUAL O ULTIMO NUMERO VISIVEL SEM ROLAR A TELA?

ESCOLHA UM TEMA OU CRIE O SEU:
1. Mansao Assombrada 🏚️
2. Estacao Espacial 🚀
3. Masmorra Medieval 🐉
4. Templo na Selva 🗿
5. Noir Cyberpunk 🌃

INFORME A LARGURA E O TEMA: > _
```

### 2. Exemplo de Cenário (80 Colunas — Antes de pegar os itens)

Em modo de 80 colunas, os cenários ganham riqueza panorâmica. Note que a **lanterna** (`🔦`), o **cartão magnético** (`💳`) e a **chave** (`🗝️`) estão visíveis na sala:

```text
SALA DE CONTROLE PRINCIPAL - SETOR ALFA              PONTOS: 010/100 | TURNO: 04
╔══════════════════════════════════════════════════════════════════════════════╗
║  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  ║
║  ░░┌────────────────────────┐░░░░░░╔══════════════════╗░░░░░░┌────────────┐░░  ║
║  ░░│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓ │░░░░░░║   🚪  [TRANCADA] ║░░░░░░│  ⚠️ ALERTA │░░  ║
║  ░░│ ▓  SISTEMA: OFFLINE  ▓ │░░░░░░║   ╔══════════╗   ║░░░░░░│  [04:12]   │░░  ║
║  ░░│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓ │░░░░░░║   ║ ░░░░░░░░ ║   ║░░░░░░└────────────┘░░  ║
║  ░░└──────────┬──┬──────────┘░░░░░░║   ║ ░░░░░░●  ║   ║░░░░░░░░░░░░░░░░░░░░  ║
║  ░░░░░░░░░░░░░│  │░░░░░░░░░░░░░░░░░║   ║ ░░░░░░░░ ║   ║░░░░░░▄████████████▄░░  ║
║  ░░▄████████████████████████▄░░░░░░╚═══╩══════════╩═══╝░░░░░░█  🔦   💳   █░░  ║
║  ░░█  [o][o][o]   🗝️   ===  █░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░█  ════════  █░░  ║
║  ▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀  ║
╚══════════════════════════════════════════════════════════════════════════════╝
Voce esta na sala de controle principal da estacao. Um monitor exibe falhas no
sistema e uma escotilha blindada bloqueia a passagem ao norte.
ITENS VISIVEIS: CHAVE ENFERRUJADA, LANTERNA TATICA, CARTAO MAGNETICO.
SAIDAS OBVIAS: SUL, OESTE.
--------------------------------------------------------------------------------
OK.
O QUE VOCE FAZ AGORA? > PEGAR CHAVE
```

### 3. Exemplo de Cenário (80 Colunas — Após pegar o item) e Inventário

Após o comando `PEGAR CHAVE`, o desenho `🗝️` desaparece automaticamente do console central na arte ASCII e da lista de `ITENS VISIVEIS`:

```text
SALA DE CONTROLE PRINCIPAL - SETOR ALFA              PONTOS: 015/100 | TURNO: 05
╔══════════════════════════════════════════════════════════════════════════════╗
║  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  ║
║  ░░┌────────────────────────┐░░░░░░╔══════════════════╗░░░░░░┌────────────┐░░  ║
║  ░░│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓ │░░░░░░║   🚪  [TRANCADA] ║░░░░░░│  ⚠️ ALERTA │░░  ║
║  ░░│ ▓  SISTEMA: OFFLINE  ▓ │░░░░░░║   ╔══════════╗   ║░░░░░░│  [04:12]   │░░  ║
║  ░░│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓ │░░░░░░║   ║ ░░░░░░░░ ║   ║░░░░░░└────────────┘░░  ║
║  ░░└──────────┬──┬──────────┘░░░░░░║   ║ ░░░░░░●  ║   ║░░░░░░░░░░░░░░░░░░░░  ║
║  ░░░░░░░░░░░░░│  │░░░░░░░░░░░░░░░░░║   ║ ░░░░░░░░ ║   ║░░░░░░▄████████████▄░░  ║
║  ░░▄████████████████████████▄░░░░░░╚═══╩══════════╩═══╝░░░░░░█  🔦   💳   █░░  ║
║  ░░█  [o][o][o]        ===  █░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░█  ════════  █░░  ║
║  ▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀  ║
╚══════════════════════════════════════════════════════════════════════════════╝
Voce esta na sala de controle principal da estacao. Um monitor exibe falhas no
sistema e uma escotilha blindada bloqueia a passagem ao norte.
ITENS VISIVEIS: LANTERNA TATICA, CARTAO MAGNETICO.
SAIDAS OBVIAS: SUL, OESTE.
--------------------------------------------------------------------------------
OK. VOCE PEGOU: CHAVE ENFERRUJADA.

INVENTARIO (1/6):
- 🗝️ CHAVE ENFERRUJADA

O QUE VOCE FAZ AGORA? > _
```

## 📂 Estrutura do Repositório

* `PROMPT.md`: O código-fonte do *System Prompt* pronto para ser copiado e colado na IA.
* `README.md`: Documentação oficial do projeto, instruções e exemplos.

## 🏷️ Versão

* **Versão Atual:** `1.2` (Fidelidade ao CP400 com ortografia ASCII de 7 bits sem acentos, interface *Split-Screen* estilo *Scott Adams*, matriz consistente de 20 a 30 salas, mecânica de escuridão/luz, inventário de 6 itens com combinação e sistema de pontuação de 0 a 100).

## 📄 Licença

Este projeto está licenciado sob a [**`Licença MIT`**](./LICENSE).
