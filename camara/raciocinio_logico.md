# RACIOCÍNIO LÓGICO-MATEMÁTICO

1. Dica

Estudar através dos vídeos e exercícios

## Material de Estudo

- https://www.youtube.com/watch?v=aCZUm9qzTo0
- https://www.youtube.com/watch?v=XbqsFXbK4jY
- https://www.youtube.com/watch?v=Kg350qEdNVE

## Lógica Proposicional

## Lógica Sequencial

- Descobre as leis de formação

### Carimbos ou Ciclos

Para questões onde existe uma sequencia de letras que se repetem:

- Exemplo:

```
Qual a 500a letra da sequência:

SALVADORBAHIASALVADORBAHIASALVADOR...
```

Resposta:

SALVADORBAHIA = 13 letras
500a letra = 500 % 13 = 6a letra
`6a letra = D`

**OBS**: para o resto = 0 o último elemento da sequêcia (Seria o A nesse caso)

### Pior Caso ou Alternativa Incontroversa ou Casa dos Pombos

- Exemplo 1

```
Em uma gaveta tem 4 meias brancas, 6 meias pretas e 8 meias azuis. Para ter certeza de que se retirou 2 meias azuis você precisa tira, no mínimo quantas meias?
```

Resposta: 

No pior caso, você tira todas as meias das outras cores. Ou seja, retira 10 meias + 2 meias azuis

- Exemplo 2

```
Há 10 livros de direito, 12 de economia e 15 de adm, você precisa tirar um livro de cada. Qual o valor mínimo para ter certeza que você tirou um de cada?
```

Resposta:

No pior caso, você retira a soma dos maiores valores + a quantidade necessária do menor valor.
Nesse caso você tira 15 + 12 + 1

### Calendários

- Exemplo

```
Certo ano, o dia 1 de agosto caiu em uma segunda. Nesse ano, o dia das crianças, 12 de outubro foi?
```

Resposta:

Sempre exclua a referência (dia 1 de agosto)
Agosto = 31 dias - referência
Set = 30 dias
Out = 12 dias
Total = 72 dias

72 % 7 = 2 dias além da segunda
`2 dias além da segunda = quarta`

### Apenas uma verdade ou mentira

- Exemplo

```
Apenas 1 diz a verdade

Miguel - "O culpado é Jaime"
Érico - "Ricardo não é culpado"
Ricardo - "O culpado é Caio"
Jaime - "Eu não sou culpado"
Caio - "O culpado é Miguel"
```

Resposta:

1. Encontrar duas falas contraditórias:
- Miguel diz que o culpado é Jaime
- Jaime diz que não é culpado
Um dos dois está dizendo a verdade, ou seja, o restante está mentindo

2. Inverter as falas dos mentirosos:
- Érico - Ricardo é culpado
- Ricardo - O culpado não é Caio
- Caio - O culpado não é Miguel

`O culpado é Ricardo`

### Soma de Termos

- Exemplo:

```
A quantidade de 'o' que tem na figura 100 é:

              o
      o      o o
o -> o o -> o o o
```

Resposta: 

1. Olhe por linha:
1a figura: 1 base
2a figura: 2 base + 1 1o andar
3a figura: 3 base + 2 1o andar + 1 2o andar

2. ou seja, na figura 100 vai ser:

100a figura: 100 + 99 + 98... + 1

3. Agora utilize a fórmula de gauss:

50 pares * 101 (que é a soma do primeiro elemento com o último) = 5050

### Problemas com Mesas

- Exemplo 1:

```
Encontram-se sentados em torno de uma mesa quadrada quatro juristas. Miranda, o mais antigo entre eles, é alagoano. Há também um paulista, um carioca e um baiano. Ferraz está sentado à direita de Miranda. Mendes, à direita do paulista. Por sua vez, Barbosa, que não é carioca, encontra-se à frente de Ferraz. Assim:

a) Ferraz é carioca e Barbosa é baiano.
b) Mendes é baiano e Barbosa é paulista.
c) Mendes é carioca e Barbosa é paulista.
d) Ferraz é baiano e Barbosa é paulista.
e) Ferraz é paulista e Barbosa é baiano.
```
Resposta:

1. Desenhar a mesa e analizar onde dá pra posicionar já as primeiras pessoas

         Mendes (carioca)
         -------
Barboza |       | Ferraz (paulista)
(baiano)|       |
         -------
          Miranda (alagoano)

`letra e`

- Exemplo 2:

```
Cinco pessoas A, B, C, D e E sentam-se em volta de uma mesa circular. Sabe-se que:

- B não é vizinho de A
- D é vizinho à esquerda de C
- B e C não são vizinhos
```

Resposta:

1. Desenhar a mesa e onde dá pra posicionar as pessoas:

          C
     D    ___
         /   \
        |     |
         \___/

 
2. Encontrar as frases que possuem a mesma pessoa
No caso, como B não é vizinho de A, nem vizinho de C então ele só pode estar entre D e E

           C
          ___
     D   /   \
        |     |  A
     B   \___/
           E

### Torneiras e Afins

- Exemplo:

```
Uma torneira enche um tanque em 3 horas, e outra enche um tanque em 4 horas, se as duas forem abertas ao mesmo tempo, elas enchem o tanque em quantas horas?
```

Resposta:

Utilizar média harmônica: 1/T1 + 1/T2 = 1/T

1/3 + 1/4 = 1/T (MMC)
(4+3)/12 = 1/T
7T = 12
T = 7horas e pouquinho

### Quantas vezes aparece um algarismo

- Qualquer algarismo de 1 a 9 aparece 20 vezes até 99

- Exemplo:

```
Um hotel de 3 andares está sendo contruído. Cada andar terá 100 quartos. Os quatos serào numerados de 100 a 399 e cada um terá seu número afixado à porta. Cada número será composto por peças individuais, cada uma simbolizando um único algarismo. Qual a quantidade mínima de peças, simbolizando o algarismo 2, necessárias para identificar o número de todos os quartos?
```

Resposta:

O algarismo 2 aparece 20 vezes de 1 a 99
O algarismo 2 aparece 20 vezes de 100 a 199
O algarismo 2 aparece 100 + 20 vezes de 200 a 299 (pq todos eles começam com 2)
O algarismo 2 aparece 20 vezes de 300 a 399

`O total = 160 vezes`