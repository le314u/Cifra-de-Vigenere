# Cifra de Vigenère

A **Cifra de Vigenère** é uma técnica de cifra polialfabética utilizada para criptografar e descriptografar mensagens. Criada por Blaise de Vigenère no século XVI, essa cifra utiliza uma chave para modificar as letras do texto original. Sua principal vantagem sobre outras cifras simples, como a Cifra de César, é que ela emprega um conjunto de substituições dinâmicas, dificultando a quebra da cifra por análise de frequência.

## Como Funciona?

Na Cifra de Vigenère, cada letra do texto é deslocada de acordo com a letra correspondente na chave. A chave é repetida, se necessário, até cobrir todo o texto. O deslocamento de cada letra depende da posição da letra da chave.

### Passo a Passo:
1. A chave é repetida até ter o mesmo comprimento do texto a ser cifrado.
2. Cada letra do texto é substituída por outra, com base no deslocamento indicado pela letra correspondente da chave.
3. O alfabeto utilizado geralmente é o padrão de 26 letras (A-Z).

### Exemplo:

Texto original: `HELLO`  
Chave: `KEY`

A tabela de deslocamento seria a seguinte:

| Letra do Texto | Letra da Chave | Deslocamento | Letra Cifrada |
|-----------------|----------------|--------------|---------------|
| H               | K              | 10           | R             |
| E               | E              | 4            | I             |
| L               | Y              | 24           | J             |
| L               | K              | 10           | V             |
| O               | E              | 4            | S             |

Texto cifrado: `RIJVS`

## Como Decifrar

Para decifrar a mensagem, o processo é inverso:
1. A chave é repetida novamente até cobrir todo o texto cifrado.
2. Cada letra do texto cifrado é "deslocada" para trás, de acordo com a letra correspondente na chave.

### Exemplo de Descriptografia:

Texto cifrado: `RIJVS`  
Chave: `KEY`

| Letra Cifrada | Letra da Chave | Deslocamento | Letra Decifrada |
|----------------|----------------|--------------|-----------------|
| R              | K              | 10           | H               |
| I              | E              | 4            | E               |
| J              | Y              | 24           | L               |
| V              | K              | 10           | L               |
| S              | E              | 4            | O               |

Texto original: `HELLO`

## Vantagens da Cifra de Vigenère
- Mais segura do que a Cifra de César, pois utiliza múltiplos deslocamentos.
- Não há padrão fixo de deslocamento, dificultando a análise de frequência.

## Desvantagens
- A segurança da Cifra de Vigenère depende fortemente da chave. Se a chave for curta ou repetitiva, pode ser vulnerável a ataques de força bruta ou análise de frequência.
- Hoje em dia, a Cifra de Vigenère é considerada fraca e obsoleta para aplicações modernas, pois algoritmos mais seguros, como AES, são preferíveis.

## Conclusão

A Cifra de Vigenère foi um marco na história da criptografia e, embora hoje seja considerada insegura, ainda é uma excelente maneira de entender os princípios básicos da criptografia. Sua técnica de substituição dinâmica fez dela uma ferramenta importante por séculos e continua sendo estudada como um exemplo de cifra polialfabética.


# Detalhes da Minha Implmentação

## Como Funciona a Criação da Chave?

A chave é construída a partir de uma string como exeomplo pegaresmo '123456789'. O processo de criação envolve os seguintes passos:

1. **Determinação do Tamanho da Chave**:
   - O número fornecido é '123456789'. O tamanho da chave é 9, que é o número de caracteres presentes.

2. **Escolha de Dois Números Primos Entre Si**:
   - A chave será dividida com base em dois números **que são primos entre si** e cuja soma é igual ao tamanho da chave (9). Os números primos são escolhidos de maneira que a soma deles seja 9 e o produto seja o maior possível.
   - Para o número 9, os dois números que atendem a essa condição são **4 e 5**, pois:
     - \(4 + 5 = 9\)
     - \(4 \times 5 = 20\)
     - E **4 e 5** são primos entre si (não têm divisores comuns além de 1).

3. **Divisão da Chave**:
   - A chave '123456789' é dividida com base nos números escolhidos (4 e 5):
     - Parte 1: '1234' (primeira parte da chave)
     - Parte 2: '56789' (segunda parte da chave)

4. **Criação do Arranjo de Pares**:
   - A partir dessas duas partes, um arranjo é gerado seguindo um padrão numérico específico:
     - Os índices são combinados de forma a formar pares: `15, 26, 37, 48, 19, 25, 36, 47, 18, 29, 35...`
     - O arranjo continua até os números se repetirem.

### Exemplo de Arranjo Criado:

| Índice A | Índice B | Par Criado |
|----------|----------|------------|
| 1        | 5        | 15         |
| 2        | 6        | 26         |
| 3        | 7        | 37         |
| 4        | 8        | 48         |
| 1        | 9        | 19         |
| 2        | 5        | 25         |
| 3        | 6        | 36         |
| 4        | 7        | 47         |
| 1        | 8        | 18         |
| 2        | 9        | 29         |
| 3        | 5        | 35         |
| ...      | ...      | ...        |

Esses pares são usados para manipular a cifra durante o processo de criptografia e decriptação.

## Porque isso?
uma chave de 9 caracteres virou uma chave de 20 pares ordenados ou seja uma chave de 40 caracteres
