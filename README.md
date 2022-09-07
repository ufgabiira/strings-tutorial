# Estruturas de Dados: Strings

Strings são muito importantes e fazem parte do dia a dia de qualquer programador. Neste guia explicaremos alguns conceitos básicos que envolvem essas estruturas.  
_Observação: Todos os nossos exemplos são pseudo-código._

## Table of Contents

- [O que são Strings?](#what)
  - [Como elas funcionam?](#how)
- [O que podemos fazer com Strings?](#can-do)
  - [Concatenação](#concat)
  - [Tamanho de uma string](#tamanho)
  - [Aparar uma string](#aparar)
  - [Encontrar substrings/caracteres](#subs)
  - [Substituir substrings/caracteres](#substituicao)
  - [Inverter](#reverse)
  - [Subsequências](#subset)
  - [Comparar](#compare)
- [Conclusão](#conclusion)

## **O que são Strings?** <a name="what"></a>

As Strings são sequências ordenadas de caracteres. Muito parecidas com os _arrays_, são exclusivas para texto, logo só armazenam caracteres.

> Em algumas linguagens, como Java e Python, as strings são tipos imutavéis, ou seja, uma vez declaradas não poderão ser alteradas. Não consideraremos isso neste tutorial mas recomendados que você mantenha isso em mente.  
> Sugerimos que leia sobre o assunto na documentação oficial da sua linguagem de escolha.

Para inicializar uma string devemos usar áspas duplas.

```pseudo
str = "Ola, mundo!"
```

**Muito cuidado para não se confundir!**

```pseudo
a = "2 + 2"
b = 2 + 2
```

_O valor de `a` é o texto "2 + 2", já o valor de `b` é o número 4, resultado da adição `2 + 2`._

### **Como elas funcionam?** <a name="how"></a>

Como nos _arrays_, as strings também possuem um valor de índice que representa cada elemento, ou caractere.

Considere o trecho:

```pseudo
hello = "hello world"
```

Temos que:

|  **índice**   |  0  |  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9  | 10  |
| :-----------: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **caractere** | 'h' | 'e' | 'l' | 'l' | 'o' | ' ' | 'w' | 'o' | 'r' | 'l' | 'd' |

Dessa maneira temos que o elemento no `hello[0]` é a letra 'h', `hello[5]` é um espaço em branco, `hello[8]` é a letra 'r' e assim por diante.

## **O que podemos fazer com Strings?** <a name="can-do"></a>

Para trabalhar com strings serão necessárias operações especícas. A seguir explicaremos alguns  
dos métodos e funções mais importantes.  
_Lembre-se que cada linguagem tem sua própria sintaxe e maneira de aplicar cada uma dessas operações._

### **Concatenação** <a name="concat"></a>

O termo concatenar significa conectar algo a uma sequência, logo concatenar strings significa liga-las uma após a outra, resultando em uma única string. Observe o exemplo a seguir:

```pseudo
nome = "Fulano"
sobrenome = "de Tal"
nomeCompleto = nome + ' ' + sobrenome

print(nomeCompleto)
```

Saída:

```output
"Fulano de Tal"
```

Aqui representamos a operação como uma soma de strings, onde o último caractere da primeira string será seguido pelo primeiro caractere da segunda string e assim por diante.
_Perceba que se fizermos `nomeCompleto = nome + sobrenome` teremos como resultado uma string de valor `"Fulanode Tal"`_

### **Tamanho de uma string** <a name="tamanho"></a>

A prática de encontrar o tamanho/comprimento de uma string é muito comum na programação, frequentemente nos deparamos com algum problema que para ser resolvido devemos saber o comprimento total da string para percorrê-la, por exemplo. Sob essa ótica, a linguagem python tem a função interna "len" que retorna o tamanho da string.

**Exemplo:**

```pseudo
str = "Hello world!"

print(len(str))
```

Saída:

```output
12
```

Como resultado, temos o valor 12. Entretanto, é possível observar que embora só exista 11 letras, o resultado apontou um elemento a mais, esse elemento corresponde ao "espaço" entre as letras "o e w", que para a função significa um caractere especial.

#### Método 2

Podemos encontrar o tamanho da string em bytes, usando a biblioteca de funções "sys", através do método “getsizeof”, da seguinte forma:

**Exemplo:**

```pseudo
import sys

texto = "Hello World!"
res = sys.getsizeof(texto)

print(res)
```

Saída:

```output
61
```

O resultado será 61, que corresponde ao tamanho em bytes da string.

#### Método 3

Embora exista todas essas funções, é possível encontrar o comprimento/tamanho de forma manual, segue abaixo um exemplo:

Criamos uma estrutura de repetição, um “for”, por exemplo, que percorre cada posição da string, até o seu último elemento "\0", incrementando uma variável contadora. Ao final, o resultado da variável contadora será o tamanho/comprimento da string.

**Exemplo:**

```pseudo
x = 'Hello World!'
length = 0

for i in x:
length += 1
print(length)
```

Saída:

```output
12
```

### **Aparar uma string** <a name="aparar"></a>

Remover determinados trechos ou caracteres especiais como espaços ou hífens, por exemplo, é uma prática bem comum na manipulação de strings. Sob essa ótica, a linguagem python tem os métodos strip, rstrip e lstrip que podem ser usados para remover espaços em branco antes e depois na string.

strip(): retorna uma nova string removendo todos os espaços em branco iniciais e finais, incluindo tabulações "\t".

**Exemplo:**

```pseudo
stTeste = "    TEXTO    "
stTesteTrim = stTeste.strip()
print("[" + stTesteTrim + "]")
```

Saída:

```
[TEXTO]
```

rstrip(): tem o comportamento semelhante ao “strip”, entretanto, só remove os espaços em branco à direita da string.

**Exemplo:**

```pseudo
stTeste = "    TEXTO    "
stTesteTrim = stTeste.rstrip()
print("[" + stTesteTrim + "]")

```

Saída:

```output
[    TEXTO]
```

lstrip(): atua de forma similar ao “rstrip”, porém, só remove os espaços em branco à esquerda da string.

**Exemplo:**

```pseudo
stTeste = "    TEXTO    "
stTesteTrim = stTeste.lstrip()
print("[" + stTesteTrim + "]")
```

Saída:

```output
[TEXTO    ]
```

### **Encontrar substrings/caracteres** <a name="subs"></a>

De modo geral, uma substring é uma string dentro de outra string, na vida real, por exemplo, podemos destacar uma palavra dentro de uma frase, ou até mesmo os prefixos e sufixos que formam as palavras. Na linguagem python podemos fazer algumas operações com as substrings.

#### Método 1

find(): o método "find" retorna o índice do primeiro caracter da substring dentro da string, caso a substring não exista ele retorna "-1".

**Exemplo:**

```pseudo
substring = "Hello"
string = "Hello world!"
print(string.find(substring))
```

Saída:

```
0
```

O resultado é "0", que corresponde ao índice inicial da substring na string.

#### Método 2

rfind(): podemos usar também o método “rfind”, que retorna o último índice da substring na string.

**Exemplo:**

```pseudo
substring = "hello"
string = "hello world"
print(string.rfind(substring))
```

Saída:

```output
4
```

#### Método 3

index(): Além das funções "find e rfind", também podemos usar o método "index", que funciona de forma semelhante ao método "find", todavia quando a substring não é encontrada o método retorna "ValueError".

**Exemplo:**

```pseudo
substring = "z"
string = "Hello world"
print(string.index(substring))
```

Saída:

```output
ValueError
```

#### Método 4

Operador in: Podemos usar também o operador "in" que verifica se o operando à esquerda está contido na lista/string à direita.

**Exemplo:**

```pseudo
str = "Hello world!"
if 'Hello' in str:
print("encontrado!")
```

Saída:

```output
encontrado!
```

#### Método 5

endswith(): O método "endswhith" verifica se a substring está no final da string, caso esteja essa função retorna "true", caso contrário retorna "false".

**Exemplo:**

```pseudo
str = "Hello world"
subs="world"
str.startswith( subs )
```

Saída:

```output
true
```

##### Método 6:

startswith(): É semelhante ao "endswhith", entretanto verifica se a substring está no início da string.

**Exemplo:**

```pseudo
str = "Hello world"
subs = "Hello"
str.startswith( subs )
```

Saída:

```output
true
```

#### Método 7

count(): Com o método "count" é possível contar a quantidade de incidências da substring na string.

**Exemplo:**

```pseudo
str = "Hello world"
subs = "Hello"
str.count( subs )
```

Saída:

```output
1
```

#### Outras operações

splint(): Além de encontrar ou contar substrings, é possível criar uma lista de substrings a partir de uma string, usando a função "split".

**Exemplo:**

```pseudo
string = "Hello world!"
print(string.split())
```

Saída:

```output
['Hello', 'world!']
```

### **Substituir substrings/caracteres** <a name="substituicao"></a>

O método replace é utilizado para substituir um ou mais trechos em uma string, sendo o tipo string imutável em python, essa função retorna uma nova string, dada a modificação proposta. Esse método tem 3 parâmetros, dois obrigatórios e um opcional, que auxiliam na forma de substituição.

**Exemplo de uso com parâmetros:**

```pseudo
string.replace(valorvelho, valornovo, contador)
```

O parâmetro "valorvelho" corresponde ao valor original que será substituído ao final do processo.

O parâmetro "valornovo" corresponde ao novo valor que será inserido no lugar do "valorvelho".

O parâmetro contador corresponde a quantas vezes o processo de substituição vai ocorrer. Esse parâmetro é opcional, caso não seja inserido o método substituirá todas as ocorrências do "valorvelho" encontrados na string, pelo "valornovo".

**Exemplo:**

```python
string= "Hello, world!"
print(string.replace(",", " -"))
```

Saída:

```output
Hello - world!
```

### **Inverter e Rotacionar** <a name="reverse"></a>

Seguindo uma simples ideia, inversão (ou rotação) é a mudança na ordenação dos caracteres de uma string, onde o primeiro passa a ser o último, o segundo se torna o penúltimo e assim por diante. Tomando como exemplo uma string de 10 caracteres, a posição 0 troca com a 9, a posição 1 troca com a 8 e assim por diante.

Considere a função reverse() que recebe uma string e retorna sua inversão.

```pseudo
a = "lorem ipsum"
b = reverse(a)

print(b)
```

Saída:

```output
"muspi merol"
```

A ideia das trocas pode ser analisada perante a quantidade de índices da string. Se a quantidade for par, as trocas ocorreram de acordo com seu par ordenado característico do extremo, se a quantidade for ímpar segue a mesma ideia do anterior, porém não ocorre alteração no elemento do índice central.
Exemplos:

```pseudo
a = "estrutura"
b = "rotacionar"
c = reverse(a)
d = reverse(b)

print(c)
print(d)
```

Saída:

```output
"aruturtse"       // quantidade par, todos os elementos são invertidos
"ranoicator"      // quantidade ímpar, o elemento do meio não é alterado
```

### **Subsequências** <a name="subset"></a>

Subsequências são strings formadas a partir de qualquer combinação de caracteres da string original.  
Com isso, combinações de elementos de uma string que podem ser concatenados um a um, dois a dois, em diante, até n, onde esse n é o tamanho da string.  
Considerando a palavra "dados", podemos ter as seguintes subsequências:

```pseudo
  d, a, d, o, s, ..., da, dd, do, ..., dad, dao, das, ..., dado, dads, ..., dados, sodads, ...
```

**Não confunda:** _Substrings são subsequências da string original mas nem toda subsequência é uma substring. Isso acontece porque as subsequências não necessariamente seguem a ordenação original da string._

### **Comparar** <a name="compare"></a>

Dizemos que uma string é igual a outra quando seus caracteres são iguais e possuem a mesma ordenação. `polvo` é diferente de `povo`.  
A partir disso, temos dois possíveis cenários para nossas comparações:

1. **_case sensitive_**: Diferencia-se maiúsculas de minúsculas; ou
2. **_case insensitive_**: Não se diferencia maiúsculas de minúsculas.

Uma comparação comum será sempre _case sensitive_. Dessa forma, se quisermos comparar strings sem considerar maiúsculas e minúsculas, precisaremos considerar seus caracteres todos com o mesmo "_case_" , por assim dizer.  
Para isso, é necessário operar em todos os elementos da string, passando cada um deles para o caso desejado.

```pseudo
a = "mundo"
b = "MUNDO"

// a != b
print("a = ", a)
print("b = ", b)
```

Saída:

```output
a = "mundo"
b = "MUNDO"
```

Temos que transformar `b` para que fique somente em minúsculas ou `à` para maiúsculas. Considere uma função lower, onde lower('A') irá retornar 'a'.

```pseudo
n = size(b) // n = 5

for (i = 0; while i < n) {
  b[i] = lower(b[i])
}

// a == b
print("a = ", a)
print("b = ", b)
```

Saída:

```output
a = "mundo"
b = "mundo"
```

## **Conclusão** <a name="conclusion"></a>

Strings são de fato estruturas muito úteis no nosso dia a dia. Seu uso é essencial em bancos de dados, ferramentas de busca (como o grep, ), criação e validação de senhas, entre outras situações. Se quiser saber mais sobre as Strings acessse os links em nossas referências.

## Referências: <a name="references"></a>

- [Complete Guide on Strings With Interview Question](https://www.geeksforgeeks.org/complete-guide-on-strings-with-interview-questions/)
- [Encontre um caractere em uma string em Python](<https://www.delftstack.com/pt/howto/python/position-of-character-in-string/#:~:text=em%20uma%20string.-,Use%20a%20fun%C3%A7%C3%A3o%20find()%20para%20encontrar%20a%20posi%C3%A7%C3%A3o%20de,%C3%A9%20o%20comprimento%20da%20string>)
- [Substrings em Python – como dividir uma string](https://www.freecodecamp.org/portuguese/news/substrings-em-python-como-dividir-uma-string/)
- [Como procurar palavras em uma string com Python (substring)](https://www.horadecodar.com.br/2020/04/26/como-procurar-palavras-em-uma-string-com-python-substring/)
- [Python replace: substituindo substrings em uma string!](https://blog.betrybe.com/python/python-replace/)

---

## Este guia foi desenvolvido por

**Luiz Gustavo**  
[![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/luiz-gustavo-silva-151395205/)[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)

**Gabriel Ferreira**  
[![Dev.to blog](https://img.shields.io/badge/dev.to-0A0A0A?style=for-the-badge&logo=dev.to&logoColor=white)](https://dev.to/ufgabiira)[![LeetCode](https://img.shields.io/badge/LeetCode-000000?style=for-the-badge&logo=LeetCode&logoColor=#d16c06)](https://leetcode.com/gabriel_ferreira/)[![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ufgabiira)

**Wellder Bernardo**  
**Pedro Manoel**  
**Cipriano Jose**
