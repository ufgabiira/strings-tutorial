# Estruturas de Dados: Strings

Strings são muito importantes e fazem parte do dia a dia de qualquer programador. Neste guia explicaremos conceitos básicos e algumas aplicações que envolvem essas estruturas.

## Table of Contents

- [O que são Strings?](#what)
  - [Como elas funcionam?](#how)
- [O que podemos fazer com Strings?](#can-do)
  - [Concatenação](#concat)
  - [Encontrar substrings/caracteres](#find)
  - [Substituir substrings/caracteres](#replace)
  - [Verificar maiúsculas e minúsculas](#test-case)
- [Aplicações](#apply)

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

### Encontrar substrings/caracteres <a name="find"></a>

### Substituir substrings/caracteres <a name="replace"></a>

### Transformar (maiúsculas e minúsculas) <a name="transform"></a>

## **Aplicações** <a name="apply"></a>

Strings são de fato estruturas muito úteis no nosso dia a dia. Seu uso em bancos de dados, ferramentas de busca (como o grep), criação e validação de senhas, entre outras situações, as tornam realmente essenciais.

---

### Este guia foi desenvolvido por

**Luiz Gustavo**  
[![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/luiz-gustavo-silva-151395205/)[![Portfolio](https://img.shields.io/badge/Portfolio-%23000000.svg?style=for-the-badge&logo=firefox&logoColor=#FF7139)](https://luiz4us8av6.github.io/luiz_dev/index.html)

**Gabriel Ferreira**  
[![Dev.to blog](https://img.shields.io/badge/dev.to-0A0A0A?style=for-the-badge&logo=dev.to&logoColor=white)](https://dev.to/ufgabiira)[![LeetCode](https://img.shields.io/badge/LeetCode-000000?style=for-the-badge&logo=LeetCode&logoColor=#d16c06)](https://leetcode.com/gabriel_ferreira/)[![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ufgabiira)

**Wellder Bernardo**  
**Pedro Manoel**  
**Cipriano Jose**
