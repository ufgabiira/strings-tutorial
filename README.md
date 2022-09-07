# Estruturas de Dados: Strings

Strings são muito importantes e fazem parte do dia a dia de qualquer programador. Neste guia explicaremos conceitos básicos e algumas aplicações que envolvem essas estruturas.

## Table of Contents

- [O que são Strings?](#what)
  - [Como elas funcionam?](#how)
- [O que podemos fazer com Strings?](#can-do)
  - [Concatenação](#concat)
  - [Tamanho de uma string](#tamanho)
  - [Aparar uma string](#aparar)
  - [Encontrar substrings/caracteres](#subs)
  - [Substituir substrings/caracteres](#substituicao)
  - [Fazer buscas](#search)
    - [Expressões Regulares](#regex)
- [Fontes](#fontes)

## **O que são Strings?** <a name="what"></a>

As Strings são sequências ordenadas de caracteres. Elas são estruturas de dados muito parecidas com os _arrays_, no entanto são exclusivas para texto, logo só armazenam caracteres.

Para inicializar uma string devemos usar áspas duplas:

```pseudo
str = "Olá, mundo!"
```

**_Muito cuidado para não se confundir!_**

```pseudo
a = "2 + 2"
b = 2 + 2
```

_O valor de `a` é o texto "2 + 2", já o valor de `b` é o número 4, resultado da operação `2 + 2`._

### **Como elas funcionam?** <a name="how"></a>

Como nos _arrays_, as strings também possuem um valor de índice para cada elemento, ou caractere.

```pseudo
hello = "hello world"
```

|  **índice**   |  0  |  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9  | 10  |
| :-----------: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **caractere** | 'h' | 'e' | 'l' | 'l' | 'o' | ' ' | 'w' | 'o' | 'r' | 'l' | 'd' |

Dessa maneira temos que o elemento no índice 0 é a letra 'h', no índice 5 é um espaço em branco, no índice 8 é a letra 'r' e assim por diante.

## **O que podemos fazer com Strings?** <a name="can-do"></a>

Para trabalhar com strings serão necessárias operações especícas. A seguir explicaremos alguns  
dos métodos e funções mais importantes.  
_Lembre-se que cada linguagem tem sua própria sintaxe e maneira de aplicar cada uma dessas operações._

### **Concatenação** <a name="concat"></a>

O termo concatenar significa conectar algo a uma sequência, logo concatenar strings significa liga-las uma após a outra, resultando em uma única string.  
**Exemplo:**
```pseudo
nome = "Fulano"
sobrenome = "de Tal"
nomeCompleto = nome + ' ' + sobrenome

print(nomeCompleto)
```
Saída:
```
"Fulano de Tal"
```

### **Tamanho de uma string** <a name="tamanho"></a>
A prática de encontrar o tamanho/comprimento de uma string é muito comum na programação, frequentemente nos deparamos com algum problema que para serem resolvidos devemos saber o comprimento total da string para percorrê-la, por exemplo. Sob essa ótica, a linguagem python tem a função nativa “len” que retorna o tamanho da string.

**Exemplo:**
```pseudo
str = "Hello world!"

print(len(str))
```

Saída:
```
12
```
Como resultado, temos o valor 12. Entretanto, é possível observar que embora só exista 11 letras, o resultado apontou um elemento a mais, esse elemento corresponde ao "espaço" entre as letras "o e w", que para a função significa caracter especial.

##### Método 2:

 Podemos encontrar o tamanho da string em bytes, usando a biblioteca de funções "sys", através da função “getsizeof”, da seguinte forma: 	

**Exemplo:**
```pseudo
import sys 

texto= "Hello World!" 
res = sys.getsizeof(texto) 

print(res)
```

Saída:
```
61
```

O resultado será 61, que corresponde ao tamanho em bytes da string. 

##### Método 3:

Embora exista todas essas funções nativas, é possível encontrar o comprimento/tamanho de forma manual, segue abaixo uma dessa formas: 

Criamos uma estrutura de repetição, um “for”, por exemplo, que percorre cada caracter da string, até o seu último elemento "\0", incrementando uma variável contadora. Ao final, o resultado da variável contadora será o tamanho/comprimento da string.

**Exemplo:**
```pseudo
x = 'Hello World!'
length = 0

for i in x: 
length+=1 
print(length)
```

Saída:
```
12
```

### **Aparar uma string** <a name="aparar"></a>

Remover determinados trechos ou caracteres especiais, é uma prática bem comum na manipulação de strings, constantemente os algoritmos precisam remover espaços indesejados ou caracteres especiais, como ponto e hífen, das strings, para evitar determinados erros de conflito. Sob essa ótica, a linguagem python tem os métodos strip, rstrip e lstrip que podem ser usados para remover espaços em branco antes e depois na string.

strip(): retorna uma nova string removendo todos os espaços em branco iniciais e finais, incluindo tabulações “\t”.

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
```
[    TEXTO]
```

lstrip(): atua de forma similar ao “rstrip”, entretanto, só remove os espaços em branco à esquerda da string.

**Exemplo:**
```pseudo
stTeste = "    TEXTO    "
stTesteTrim = stTeste.lstrip() 
print("[" + stTesteTrim + "]")

```

Saída:
```
[TEXTO    ]
```


### **Encontrar substrings/caracteres** <a name="subs"></a>

De modo geral, uma substring é uma string dentro de outra string, na vida real, por exemplo, podemos destacar uma palavra dentro de uma frase, ou até mesmo os prefixos e sufixos que formam as palavras. Na linguagem python podemos fazer algumas operações com as substrings.

 ##### Método 1: 
 
 find(): A função "find" retorna o índice do primeiro caracter da substring dentro da string, caso a substring não exista ele retorna "-1".

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

##### Método 2:

rfind(): Podemos usar também o método “rfind”, que retorna o último índice da substring na string.

**Exemplo:**
```pseudo
substring = "hello"
string = "hello world" 
print(string.rfind(substring))
```

Saída:
```
4
```

##### Método 3:

index(): Além das funções “find e rfind”, também podemos usar a função “index”, que funciona de forma semelhante a função “find”, entretanto quando a substring não é encontrada a função retorna “ValueError”.

**Exemplo:**
```pseudo
substring = "z"
string = "hello world" 
print(string.index(substring))
```

Saída:
```
ValueError
```

##### Método 4:

Operador in: Podemos usar também o operador "in" que verifica se o operando à esquerda está contido na lista/string à direita. 

**Exemplo:**
```pseudo
str = "hello world!"
if 'hello' in str:
	print(“encontrado!”)
```
Saída:
```
encontrado!
```

##### Método 5:

endswith(): A função "endswhith" verifica se a substring está no final da string, caso esteja essa função retorna "true", caso contrário retorna "false".


**Exemplo:**
```pseudo
str = "hello world"
	subs="world"
str.startswith( subs )
```
Saída:
```
true
```

##### Método 6:

startswith(): É semelhante a função “endswhith”, entretanto verifica se a substring está no início da string.

**Exemplo:**
```pseudo
str = "hello world"
	subs="hello"
str.startswith( subs )
```
Saída:
```
true
```

##### Método 7:

count(): Com a função "count" é possível contar a quantidade de incidências da substring na string.


**Exemplo:**
```pseudo
str = "hello world"
	subs = "hello"
str.count( subs )
```
Saída:
```
1
```

#### Outras operações:

splint(): Além de encontrar ou contar substrings, é possível criar uma lista de substrings a partir de uma string, usando a função "splint".

**Exemplo:**
```pseudo
string = "hello world" 
print(string.split())
```
Saída:
```
['hello', 'world']
```

### **Substituir substrings/caracteres** <a name="substituicao"></a>

O método replace é utilizado para substituir um ou mais trechos em uma string, sendo o tipo string imutável em python, essa função retorna uma nova string, dada a modificação proposta. Esse método tem 3 parâmetros, dois obrigatórios e um opcional, que auxiliam na forma de substituição. 

**Exemplo de uso com parâmetros:**
```pseudo
string.replace(valorvelho, valornovo, contador)
```

O parâmetro “valorvelho” corresponde ao valor original que será substituído ao final do processo. 

O parâmetro “valornovo” corresponde ao novo valor que será inserido no lugar do “valorvelho”, 

O parâmetro contador corresponde a quantas vezes o processo de substituição vai ocorrer. Esse parâmetro é opcional, caso não seja inserido o método substituirá todas as ocorrências do “valorvelho” encontrados na string, pelo “valornovo”.  

**Exemplo:**
```pseudo
string= "hello, world" 
print(string.replace(",", " -")) 

```
Saída:
```
hello - world
```


### Transformar (maiúsculas e minúsculas) <a name="transform"></a>

### Fazer buscas <a name="search"></a>

#### Expressões regulares <a name="regex"></a>


## **Fontes** <a name="fontes"></a>

https://www.delftstack.com/pt/howto/python/position-of-character-in-string/#:~:text=em%20uma%20string.-,Use%20a%20fun%C3%A7%C3%A3o%20find()%20para%20encontrar%20a%20posi%C3%A7%C3%A3o%20de,%C3%A9%20o%20comprimento%20da%20string

https://www.freecodecamp.org/portuguese/news/substrings-em-python-como-dividir-uma-string/

https://www.horadecodar.com.br/2020/04/26/como-procurar-palavras-em-uma-string-com-python-substring/

https://blog.betrybe.com/python/python-replace/


---

### Este guia foi desenvolvido por

**Gabriel Ferreira**
[![image](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ufgabiira)[![image](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/gab_iira)[![image](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/gabriel_ffreire)

**Pedro Manoel**
[![image](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)[![image](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)[![image](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/)

**Luiz Gustavo**
[![image](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)[![image](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)[![image](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/luiz._.jpg/)

**Cipriano Jose**
[![image](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)[![image](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)[![image](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/)

**Wellder Bernardo**
[![image](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)[![image](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)[![image](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/)
