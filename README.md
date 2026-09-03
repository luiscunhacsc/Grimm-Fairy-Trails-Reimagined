# Grimm Fairy Trails Reimagined

Uma recriação moderna e jogável de **Grimm's Fairy Trails**, originalmente publicado para ZX81/Timex Sinclair 1000.

## Jogar

Não requer instalação nem ligação à Internet.

1. Descarrega ou clona este repositório.
2. Abre `Grimm.html` num navegador moderno.
3. Seleciona uma das seis velocidades e entra no labirinto.

## Controlos

- Setas ou `WASD`: mover Billy
- `Espaço`: pausar ou continuar
- `R`: recomeçar
- Em dispositivos táteis estão disponíveis botões direcionais.

## Objetivo

Recolhe 250 cristais enquanto evitas Murph e Drago. A Pedra de Ross, no recinto central, concede uma vida extra uma única vez.

## Fidelidade do mapa

O mapa de 32 × 16 foi extraído do programa `.p` preservado. As rotinas Z80 originais de desenho foram executadas e o resultado foi comparado com o array incorporado no jogo: **512 de 512 células coincidem**.

O original desenha 251 pontos, apesar de terminar quando o contador chega a 250. A recriação conserva os 251 pontos e o objetivo original de 250. O método, as contagens, o hash da fonte e o mapa textual estão documentados em [VALIDACAO_DO_MAPA.md](VALIDACAO_DO_MAPA.md).

Fontes:

- [ZX81 Stuff — Grimm's Fairy Trails](https://www.zx81stuff.org.uk/zx81/tape/GrimmsFairyTrails)
- [Timex/Sinclair Computers — Grimm's Fairy Trails](https://www.timexsinclair.com/computer_media/grimms-fairy-trails/index.html)

## Adaptações modernas

O labirinto, as posições iniciais, as seis velocidades, os perseguidores e a vida extra foram preservados. Os gráficos, animações, interpolação de movimento, IA determinística, pausa automática e breve proteção após perder uma vida são adaptações modernas. Esta é uma recriação jogável, não uma emulação integral do processador ZX81.

O jogo usa apenas HTML, CSS e JavaScript, todos incorporados num único ficheiro.
