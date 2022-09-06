# Estruturas de Dados: Strings

Strings são muito importantes e fazem parte do dia a dia de qualquer programador. Neste guia explicaremos conceitos básicos e algumas aplicações que envolvem essas estruturas.

## Table of Contents

- [O que são Strings?](#what)
  - [Como elas funcionam?](#how)
- [O que podemos fazer com Strings?](#cando)
  - [Concatenação](#concat)
  - [Encontrar substrings/caracteres](#find)
  - [Substituir substrings/caracteres](#replace)
  - [Fazer buscas](#search)
    - [Expressões Regulares](#regex)

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

Como nos <i>arrays</i>, as strings também possuem um valor de índice para cada elemento, ou caractere.

```pseudo
hello = "hello world"
```

|  **índice**   |  0  |  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9  | 10  |
| :-----------: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **caractere** | 'h' | 'e' | 'l' | 'l' | 'o' | ' ' | 'w' | 'o' | 'r' | 'l' | 'd' |

Dessa maneira temos que o elemento no índice 0 é a letra 'h', no índice 5 é um espaço em branco, no índice 8 é a letra 'r' e assim por diante.

## **O que podemos fazer com Strings?** <a name="cando"></a>

Para trabalhar com strings serão necessárias operações especícas. A seguir explicaremos alguns  
dos métodos e funções mais importantes.  
_Lembre-se que cada linguagem tem sua própria sintaxe e maneira de aplicar cada uma dessas operações._

### **Concatenação** <a name="concat"></a>

O termo concatenar significa conectar algo a uma sequência, logo concatenar strings significa liga-las uma após a outra, resultando em uma única string.

```python
nome = "Fulano"
sobrenome = "de Tal"
nomeCompleto = nome + ' ' + sobrenome

print(nomeCompleto)
```

Saída:

```python
Fulano de Tal
```

### Utilizar índices (como em arrays) <a name="indexes"></a>

### Encontrar substrings/caracteres <a name="find"></a>

### Substituir substrings/caracteres <a name="replace"></a>

### Transformar (maiúsculas e minúsculas) <a name="transform"></a>

### Fazer buscas <a name="search"></a>

#### Expressões regulares <a name="regex"></a>

---

### Este guia foi desenvolvido por

**Gabriel Ferreira**
[![image](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ufgabiira)

[![image](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/gab_iira)

[![image](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/gabriel_ffreire)

**Pedro Manoel**
[![image](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)

[![image](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)

[![image](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/)

**Luiz Gustavo**
[![image](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)

[![image](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)

[![image](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/)

**Cipriano Jose**
[![image](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)

[![image](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)

[![image](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/)

**Wellder Bernardo**
[![image](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)

[![image](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)

[![image](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/)  
