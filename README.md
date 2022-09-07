# Estruturas de Dados: Strings

Strings são muito importantes e fazem parte do dia a dia de qualquer programador. Neste guia explicaremos alguns conceitos básicos que envolvem essas estruturas.  
_Observação: Todos os nossos exemplos são pseudo-código._

## Table of Contents

- [O que são Strings?](#what)
  - [Como elas funcionam?](#how)
- [O que podemos fazer com Strings?](#can-do)
  - [Concatenação](#concat)
  - [Encontrar substrings/caracteres](#find)
  - [Substituir substrings/caracteres](#replace)
  - [Comparar](#compare)
- [Conclusão](#conclusion)

## **O que são Strings?** <a name="what"></a>

As Strings são sequências ordenadas de caracteres. Muito parecidas com os _arrays_, são exclusivas para texto, logo só armazenam caracteres.  
>Em algumas linguagens, como Java e Python, as strings são tipos imutavéis, ou seja, uma vez declaradas não poderão ser alteradas. Não consideraremos isso neste tutorial mas recomendados que você mantenha isso em mente.  
>Sugerimos que leia sobre o assunto na documentação oficial da sua linguagem de escolha.

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

### **Encontrar substrings/caracteres** <a name="find"></a>

### **Substituir substrings/caracteres** <a name="replace"></a>

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
"mundo"
"mundo"
```


## **Conclusão** <a name="conclusion"></a>

Strings são de fato estruturas muito úteis no nosso dia a dia. Seu uso é essencial em bancos de dados, ferramentas de busca (como o grep, ), criação e validação de senhas, entre outras situações. Se quiser saber mais sobre as Strings acessse os links em nossas referências.
  
## Referências: <a name="references"></a>

- [Complete Guide on Strings With Interview Question](https://www.geeksforgeeks.org/complete-guide-on-strings-with-interview-questions/)

---

### Este guia foi desenvolvido por

**Luiz Gustavo**  
[![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/luiz-gustavo-silva-151395205/)[![Portfolio](https://img.shields.io/badge/Portfolio-%23000000.svg?style=for-the-badge&logo=firefox&logoColor=#FF7139)](https://luiz4us8av6.github.io/luiz_dev/index.html)

**Gabriel Ferreira**  
[![Dev.to blog](https://img.shields.io/badge/dev.to-0A0A0A?style=for-the-badge&logo=dev.to&logoColor=white)](https://dev.to/ufgabiira)[![LeetCode](https://img.shields.io/badge/LeetCode-000000?style=for-the-badge&logo=LeetCode&logoColor=#d16c06)](https://leetcode.com/gabriel_ferreira/)[![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ufgabiira)

**Wellder Bernardo**  
**Pedro Manoel**  
**Cipriano Jose**
