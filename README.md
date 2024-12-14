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

## Referências

- "Cryptography and Network Security", William Stallings.
- "The Code Book", Simon Singh.
