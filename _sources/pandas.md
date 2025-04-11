# Básico de Pandas

Este módulo apresenta uma visão geral das funcionalidades fundamentais da biblioteca Pandas em Python, voltada para iniciantes.

## 1. O que é Pandas?

Pandas é uma biblioteca de código aberto para manipulação e análise de dados. Ela oferece estruturas de dados eficientes (Series e DataFrame) e diversas funções para leitura, limpeza, transformação e agregação de dados.

## 2. Instalação

Para instalar o Pandas, utilize o pip:
```bash
pip install pandas
```

## 3. Importando o Pandas
Usamos o `import` para chamar a biblioteca em nosso código. O `as` é utilizado para criar um "apelídio" para a biblioteca, sendo uma forma mais simples de chamar a função posteriormente no código.
```python
import pandas as pd
```

## 4. Estruturas de Dados Principais

4.1 Series

Uma Series é um array unidimensional rotulado. Ela pode conter qualquer tipo de dado (inteiros, strings, floats, etc.).
```python
s = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
print(s)
```
O código acima cria uma Series com rótulos personalizados. A saída será:
```bash
a    10
b    20
c    30
dtype: int64
```

## 4.2 DataFrame

Um DataFrame é uma tabela bidimensional, semelhante a uma planilha, com linhas e colunas. Ele pode conter diferentes tipos de dados em cada coluna.
```python
df = pd.DataFrame({
    'Produto': ['Arroz', 'Feijão', 'Macarrão'],
    'Preço': [20.0, 7.5, 5.0],
    'Estoque': [50, 100, 200]
})
print(df)
```
O código acima cria um DataFrame com três colunas: Produto, Preço e Estoque. A saída será:
```bash
    Produto  Preço  Estoque
0     Arroz   20.0       50
1    Feijão    7.5      100
2  Macarrão    5.0      200
```

## 5. Leitura e Escrita de Dados
Abaixo estão os principais métodos de ler e salvar arquivos com Pandas.

5.1 CSV
```python
df = pd.read_csv('dados.csv')         # lê o arquivo CSV
df.to_csv('saida.csv', index=False)   # salva o DataFrame em CSV
```

5.2 Excel
```python
df = pd.read_excel('dados.xlsx', sheet_name='Plan1')  # lê o arquivo Excel
df.to_excel('saida.xlsx', index=False)                # salva o DataFrame em Excel
```

5.3 Outros formatos

`parquet:` pd.read_parquet, df.to_parquet

`JSON:` pd.read_json, df.to_json

`HTML:` pd.read_html

`SQL:` pd.read_sql

## 6. Inspeção Inicial dos Dados
Algumas funções úteis para inspecionar os dados logo após a leitura do arquivo:
```python
print(df.head())      # primeiras 5 linhas
print(df.tail(3))     # últimas 3 linhas
print(df.shape)       # linhas e colunas
print(df.info())      # tipos e valores nulos
print(df.describe())  # estatísticas descritivas
```

## 7. Seleção e Filtragem

7.1 Seleção de Colunas
```python
precos = df['Preço']
```

7.2 Seleção de Linhas por Índice

```python
linha0 = df.loc[0]      # rótulo
linha1 = df.iloc[1]     # posição
```
7.3 Fatiamento
```python
sub_df = df.loc[0:2, ['Produto', 'Preço']]
```
7.4 Filtragem Condicional
```python
filtro = df[df['Estoque'] > 100]
```
## 8. Operações e Transformações

8.1 Adicionar e Remover Colunas
```python
df['Valor Total'] = df['Preço'] * df['Estoque'] # cria coluna chamada 'Valor Total'
df.drop('Valor Total', axis=1, inplace=True)    # remove a coluna 'Valor Total'
```
8.2 Renomear Colunas
```python
df.rename(columns={'Preço': 'Valor Unitário'}, inplace=True)
```
8.3 Ordenação
```python
df_sorted = df.sort_values(by='Preço', ascending=False)
```
8.4 Aplicar Funções
```python
df['Preço Desconto'] = df['Preço'].apply(lambda x: x * 0.9)
```
## 9. Agrupamento e Agregação
```python
grupo = df.groupby('Produto')['Estoque'].sum()
print(grupo)

df_agg = df.groupby('Produto').agg({
    'Preço': 'mean',
    'Estoque': 'sum'
})
print(df_agg)
```
## 10. Mesclagem e Concatenação

10.1 Concatenação (append)
```python
df1 = pd.DataFrame({'A': [1, 2]})
df2 = pd.DataFrame({'A': [3, 4]})
df_concat = pd.concat([df1, df2], ignore_index=True)
```
10.2 Merge (join)
```python
df_left = pd.DataFrame({'Chave': [1, 2], 'Valor1': ['X', 'Y']})
df_right = pd.DataFrame({'Chave': [1, 2], 'Valor2': ['Z', 'W']})
df_merged = pd.merge(df_left, df_right, on='Chave', how='inner')
```
## 11. Tratamento de Valores Ausentes
```python
df.dropna(inplace=True)      # remove linhas com NA
# ou
df.fillna(0, inplace=True)   # substitui NA por 0
```
## 12. Estatísticas e Descrições
```python
print(df['Preço'].mean())       # média
print(df['Estoque'].median())   # mediana
print(df['Preço'].std())        # desvio padrão
```
