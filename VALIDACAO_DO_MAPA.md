# Grimm — validação do labirinto original

## Resultado

O labirinto incorporado em `Grimm.html` coincide nas **512 células** (32 colunas × 16 linhas) com o ecrã produzido pelo programa preservado para ZX81/TS 1000.

- Paredes: **227**
- Células transitáveis: **285**
- Pontos desenhados pela inicialização: **251**
- Células transitáveis vazias: **34**
- Objetivo do código original: **250** pontos

## Fonte primária e extração

Foi descarregado o ficheiro P preservado no arquivo ZX81 Stuff:

- Página: <https://www.zx81stuff.org.uk/zx81/tape/GrimmsFairyTrails>
- Ficheiro: `grimmsfairytrails.p`
- Tamanho: 9 331 bytes
- SHA-256: `cbc402b385353bf5c7a500877a11a374d520435dce56df75f11ca2a88dd17f12`

O ficheiro foi carregado na memória a partir de 16393, como um programa ZX81. As rotinas Z80 originais foram executadas, na mesma ordem da listagem BASIC:

1. `USR 16608`: prepara o ecrã;
2. `USR 16642`: desenha os pontos;
3. instruções `PRINT` das linhas 1011–1018: abrem o corredor inferior e o centro;
4. `USR 16664`: desenha a estrutura central;
5. duas chamadas `USR 16750`: desenham as barreiras horizontais;
6. instruções `PRINT` das linhas 1049–1053: repõem cinco pontos/segmentos;
7. recorte das linhas 1–16 e das 32 colunas do ecrã.

Os endereços e os parâmetros foram conferidos com a listagem BASIC preservada na página da Timex/Sinclair: <https://www.timexsinclair.com/computer_media/grimms-fairy-trails/index.html>.

## Comparação independente

Depois da execução Z80, cada byte da área de jogo foi convertido sem interpretação geométrica: `128` para parede, `27` para ponto e `0` para célula vazia. O resultado foi comparado, célula a célula, com o array `MAP` no HTML. Também foram verificados:

- as 16 linhas têm exatamente 32 células;
- o perímetro tem 92 paredes;
- Billy começa na coluna 16, linha 15;
- Murph e Drago começam nas colunas 16 e 15, linha 6;
- a Pedra de Ross fica na coluna 16, linha 9;
- todas as posições usam as coordenadas de ecrã do ZX81, a partir de zero.
- uma travessia exaustiva a partir da posição inicial alcança as 285 células transitáveis, os 251 pontos e a Pedra de Ross.

## Mapa resultante

`#` representa parede, `·` representa ponto e o espaço representa chão vazio.

```text
################################
#······························#
#·#·##·##·##·##·##·##·##·##·##·#
#······························#
#·##·##·##·##·##·##·##·##·##·#·#
#······························#
#·#·#·#·#·#·#·####·#·#·#·#·#·#·#
#·#·#·#·#·#·#··  #·#·#·#·#·#·#·#
#·#·#·#·#·#·#·#  #·#·#·#·#·#·#·#
#·#·#·#·#·#·#·####·#·#·#·#·#·#·#
#······························#
#·#·##·##·##·##·##·##·##·##·##·#
#······························#
#·##·##·##·##·##·##·##·##·##·#·#
#                              #
################################
```

## Regras e adaptações

O manual digitalizado confirma as seis velocidades, os 250 B-lers, os dois perseguidores e a vida extra associada à Pedra de Ross. O código, porém, desenha 251 pontos e termina quando o contador chega a 250. A recriação conserva ambos os factos: não elimina uma célula para fazer a contagem parecer regular.

O labirinto, as posições iniciais, as velocidades e os elementos do original foram preservados. Os gráficos, interpolação de movimento, IA determinística, camada persistente dos cristais, pausa automática e breve proteção após perder uma vida são adaptações modernas. Esta versão é uma recriação jogável e não uma emulação integral do processador.
