# YoloDetection
Configuração e explicação de como usar o YOLO para fazer detecção de objetos.
Explaining and setting up YOLO to make objetc detection.

## O que é YOLO? (You only look once)
É um sistema de detecção de objetos em tempo real
  - Rapidez
  - Precisão
  - Código livre

Você passa a rede neural (classificador) apenas uma vez de forma completa

Classificador: recebe a imagem e processa o que ela é
Detector: identifica a posição dos objetos

## Etapas do funcionaento do YOLO

1. Se baseia na ideia de segmentar uma imagem em imagensn menores
2. Divide a imagem em uma grade SxS
3. Cada célula recebe uma caixa delimitadora e prevê a pontuação de confiança para cada caixa ([0,1])
4. Uma pontuação de confiança é retornada

> [!NOTE]
> Pontuação de confiança: o quanto de certeza o algoritmo tem que aquela célula contém um objeto e a precisão da caixa

5. Cada caixa possui 5 previsões :x,y,w,h e confiança.

## Características
- Utiliza uma arquitetura de rede neural covolucional (CNN) - Darkent
- Framework para implementar o próprio YOLO - Darknet

> [!IMPORTANT]
> Precisamos de uma GPU para rodar o YOLO de forma eficiente.

## Pastas
1. YOLO1 - Detecção de objetos
2. YOLO2 - Treinamemnto de YOLO
