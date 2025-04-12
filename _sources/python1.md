# Python Básico
Neste modulo, abordaremos os conceitos básicos de Python, essenciais para o entendimento do Seaborn e da análise de dados em geral. Vamos explorar os principais tipos de dados, operadores, estruturas de controle e funções.
## 1. O que é Python?

Python é uma linguagem de programação de alto nível, interpretada, de tipagem dinâmica e sintaxe simples. É muito usada em desenvolvimento web, ciência de dados, automação, scripts e muito mais.

## 2. Primeiros Passos
Usaremos o Google Colab para executar os códigos.
Acesse [Google Colab](https://colab.research.google.com/) e crie um novo notebook.

Iniciaremos com o print, uma função básica para exibir mensagens na tela. Por exemplo:
```python
print("Olá, mundo!")
```
O resultado do código acima será:
```bash
Olá, mundo!
```

## 3. Tipos de Dados Principais

* **Números:** `int` (inteiro), `float` (ponto flutuante/decimal)
```python
idade = 30       # int
preco = 19.90    # float
```

* **Strings:** são texto entre aspas, podendo ser aspas simples ou duplas. Podem conter letras, números e símbolos.
```python
nome = "Alice"
mensagem = 'Olá, mundo!'
```

* **Booleanos:** True (verdadeiro), False (falso). Serve para representar estados lógicos, como ligado/desligado, verdadeiro/falso.
```python
ligado = True
desligado = False
```

* **Listas:** sequência ordenada, representadas por colchetes. Podem conter diferentes tipos de dados.
```python
frutas = ["maçã", "banana", "laranja"]
numeros = [1, 2, 3, 4, 5]
```

* **Tuplas:** sequência imutável, sendo assim, não podem ser alteradas após a criação. Representadas por parênteses.
```python
coordenadas = (10.0, 20.0)
```

* **Dicionários:** pares chave-valor, representados por chaves. Permitem armazenar dados de forma estruturada.
```python
pessoas = {
    "pessoa1": {"nome": "Alice", "idade": 30},
    "pessoa2": {"nome": "Bob", "idade": 25}
}
```

## 4. Operadores Básicos

Aritméticos: `+`, `-`, `*`, `/`, `//` (divisão inteira), `%` (módulo/resto da divisão), `**` (potência).

Comparação: igual `==`, diferente `!=`, maior que`>`, menor que `<`, maior ou igual`>=`, menor ou igual `<=`

```{note}
Um igual `=` é atribuição, dois iguais `==` é comparação.
```

Lógicos: `and`, `or`, `not`.

```python
x = 10
y = 3
print(x + y)   # 13
print(x ** y)  # 1000
print(x > y and y > 0)  # True
```

## 5. Estruturas de Controle

5.1 Condicionais
```python
idade = 18
if idade >= 18:
    print("Você é maior de idade.")
else:
    print("Você é menor de idade.")
```

5.2 Laços de Repetição

for: permite iterar sobre uma sequência (lista, tupla, string).
```python
for i in range(5):
    print(i)
```

while: executa enquanto a condição for verdadeira.
```python
contador = 0
while contador < 5:
    print(contador)
    contador += 1
```

## 6. Funções

Definição e chamada de funções:
```python
def soma(a, b):
    return a + b

resultado = soma(2, 3)
print(resultado)  # 5
```
## 7. Módulos e Pacotes

Importar módulo, exemplo com o módulo `math`:
```python
import math
print(math.sqrt(16))  # 4.0
```
Instalar pacotes, exemplo com o pacote `pandas`:
```bash
pip install pandas
```
Importar pacote `pandas` e criar um DataFrame:
```python
import pandas as pd
data = pd.DataFrame({'coluna1': [1, 2, 3], 'coluna2': [4, 5, 6]})
```