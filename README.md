# TCC-Experimental-study-of-optimization-algorithms

## Dados sobre o problema

- Braço robótico de 8 eixos que pode imprimir um pixel do cartão por vez
- Mover o braço e mudar a cor é caro
- É preciso gastar o mínimo de tempo possível
- Cada elo do braço da impressora pode ser movido independentemente a cada etapa

## Dados sobre a avaliação

- Um braço robótico com oito links com comprimentos [64,32,16,8,4,2,1,1] deve "imprimir" cada ponto de uma imagem com dimensões 257*257
- A configuração do braço é descrita por uma lista de vetores de deslocamento, como [(64, -44), (32,10), (-2,16),...,(0,1),(-1,0)], onde um vetor (x,y)de tamanho l deve satisfazer max(|x|, |y|)=l
	- Essa condição significa que pelo menos um dos componentes do vetor deve ser igual a mais (positivo) ou menos (negativo) o comprimento do vetor.
- A posição do braço é a soma desses vetores de deslocamento e indica a localização da ponta do braço
- A base do braço (a origem do primeiro vetor) está em (0,0), que é o ponto médio da imagem
- O braço pode ser reconfigurado passo a passo girando qualquer um ou todos os links em uma unidade
	- Incidindo em um custo total de reconfiguração igual à raiz quadrada do número de links alterados
	- Além disso, incorre em um custo de cor igual à soma das diferenças absolutas nos componentes de cor de uma etapa para a próxima e multiplicada por um fator de escala de 3,0

### Arquivo de Envio

- O arquivo de submissão deve conter uma seqüência de configurações com os componentes de cada vetor de deslocamento delimitado por ponto e vírgula, assim: x0 y0;x1 y1;...
	- A primeira e a última configurações devem ser 64 0;-32 0;-16 0;-8 0;-4 0;-2 0;-1 0;-1 0.
	- O conjunto de posições indicadas pelas configurações deve ser igual ao conjunto de pontos da imagem. (Em outras palavras, a ponta do braço deve se mover por toda a imagem.)
	- Todos os números devem ser inteiros.

#### Exemplo

##### Configuration
```
64 0;-32 0;-16 0;-8 0;-4 0;-2 0;-1 0;-1 0
64 -1;-32 0;-16 0;-8 0;-4 0;-2 0;-1 0;-1 0
64 -2;-32 0;-16 0;-8 0;-4 0;-2 0;-1 0;-1 0
...
64 0;-32 0;-16 0;-8 0;-4 0;-2 0;-1 0;-1 0
```

## Objetivo

- A tarefa é encontrar uma sequência de configurações com posições em todos os pontos da imagem da solução com um custo mínimo.

## Kaggle

[Santa 2022 - The Christmas Card Conundrum](https://www.kaggle.com/competitions/santa-2022/overview)

[Getting Started with Santa 2022](https://www.kaggle.com/code/ryanholbrook/getting-started-with-santa-2022/notebook)

[Winner](https://www.kaggle.com/competitions/santa-2022/discussion/379167)

[GitHub Winner](https://github.com/chettub/santa2022)
