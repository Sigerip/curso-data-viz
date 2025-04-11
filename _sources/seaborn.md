# Seaborn

neste modulo vamos aprender a usar a biblioteca seaborn, que é uma biblioteca de visualização de dados baseada no matplotlib. O seaborn fornece uma interface de alto nível para criar gráficos estatísticos atraentes e informativos. Veremos como personalizar os gráficos com cores, estilos e tamanhos diferentes. O seaborn também oferece suporte a conjuntos de dados integrados, o que facilita a prática e a experimentação com diferentes tipos de visualizações.

## Instalação do Seaborn

Inicialmente iremos instalar a biblioteca seaborn. Como iremos usar o [Google Colab](https://colab.research.google.com/), usamos o `%` para executar o comando diretamente no terminal. Com isso execute o seguinte comando no seu notebook:
```bash
%pip install seaborn
```

## Importando o Seaborn
Após a instalação, podemos importar a biblioteca seaborn. O seaborn é importado como `sns` para facilitar posteriormente. Além disso, também importamos o matplotlib para exibir os gráficos. O comando para importar o seaborn é:
```python
import seaborn as sns
```

## importando a primeira base de dados
Para começar a usar o seaborn, vamos importar uma base de dados que já vem com a biblioteca. O seaborn possui várias bases de dados integradas que podem ser usadas para praticar e experimentar diferentes tipos de visualizações. Para isso, usamos o seguinte comando:
```python
data = sns.load_dataset("car_crashes")
print(data.head())
```
saída:
```python
   total  speeding  alcohol  not_distracted  no_previous  ins_premium
0   18.8     7.332    5.640          18.048       15.040       784.55   
1   18.1     7.421    4.525          16.290       17.014      1053.48   
2   18.6     6.510    5.208          15.624       17.856       899.47   
3   22.4     4.032    5.824          21.056       21.280       827.34   
4   12.0     4.200    3.360          10.920       10.680       878.41
```
Com esses comandos estamos carregando a base de dados "car_crashes" do seaborn e exibindo as 5 primeiras linhas. Essa base de dados contém informações sobre acidentes de carro, incluindo variáveis como número de acidentes, número de mortes, número de feridos, entre outras. Você pode explorar a base de dados para entender melhor os dados que ela contém. Além disso, você pode usar o comando `data.info()` para obter mais informações sobre as colunas e os tipos de dados presentes na base de dados.
