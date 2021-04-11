# Lendo e escrevendo textos


```python
import pandas as pd


# read_csv é uma função para ler tabelas de arquivos .csv
teste = pd.read_csv('TESTE.csv')
teste
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID;Nomes;Senhas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1;Raphael;159357</td>
    </tr>
    <tr>
      <th>1</th>
      <td>;;</td>
    </tr>
    <tr>
      <th>2</th>
      <td>;;</td>
    </tr>
    <tr>
      <th>3</th>
      <td>;;</td>
    </tr>
    <tr>
      <th>4</th>
      <td>;;</td>
    </tr>
  </tbody>
</table>
</div>




```python
# read_table ler tabelas de qualquer tipo de arquivo, incluindo
# arquivos com extensão .txt
teste = pd.read_table('TESTE.csv', sep=',')
teste
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID;Nomes;Senhas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1;Raphael;159357</td>
    </tr>
    <tr>
      <th>1</th>
      <td>;;</td>
    </tr>
    <tr>
      <th>2</th>
      <td>;;</td>
    </tr>
    <tr>
      <th>3</th>
      <td>;;</td>
    </tr>
    <tr>
      <th>4</th>
      <td>;;</td>
    </tr>
  </tbody>
</table>
</div>




```python
# através do argumento names podemos especificar os nomes das
# nossas colunas
names = ['ID', 'Nomes']
teste = pd.read_csv('teste2.csv', names=names)
teste
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Nomes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1;</td>
      <td>Raphael</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2;</td>
      <td>Jhonathan</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3;</td>
      <td>Isabella</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4;</td>
      <td>João</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5;</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Através de index_col podemos especificar qual coluna será
# a coluna id do nosso DataFrame
names = ['ID', 'Nomes']
teste = pd.read_csv('teste2.csv', names=names, index_col='ID')
teste
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Nomes</th>
    </tr>
    <tr>
      <th>ID</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1;</th>
      <td>Raphael</td>
    </tr>
    <tr>
      <th>2;</th>
      <td>Jhonathan</td>
    </tr>
    <tr>
      <th>3;</th>
      <td>Isabella</td>
    </tr>
    <tr>
      <th>4;</th>
      <td>João</td>
    </tr>
    <tr>
      <th>5;</th>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
names = ['ID', 'Nomes']
teste = pd.read_csv('teste2.csv', names=names, index_col='ID')
teste
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Nomes</th>
    </tr>
    <tr>
      <th>ID</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1;</th>
      <td>Raphael</td>
    </tr>
    <tr>
      <th>2;</th>
      <td>Jhonathan</td>
    </tr>
    <tr>
      <th>3;</th>
      <td>Isabella</td>
    </tr>
    <tr>
      <th>4;</th>
      <td>João</td>
    </tr>
    <tr>
      <th>5;</th>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# As vezes em um arquivo de texto podemos encontrar dados semi-estruturados
# separados por uma desingual quantidade de espaços, nestes casos
# usamos o argumento sep = '\s+'
names = ['ID', 'Nomes', 'Senha']
teste = pd.read_table('Table.txt', names=names, index_col='ID', sep='\s+')
teste
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Nomes</th>
      <th>Senha</th>
    </tr>
    <tr>
      <th>ID</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Raphael</td>
      <td>165414788&amp;</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jhonathan</td>
      <td>41544784</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Tobias</td>
      <td>544145</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Paula</td>
      <td>89987809</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Com o argumento skiprows posso ignorar linhas de um arquivo 
# de texto.
teste = pd.read_table('teste2.csv', skiprows=[1])
teste
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>1;,Raphael</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3;,Isabella</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4;,João</td>
    </tr>
    <tr>
      <th>2</th>
      <td>5;</td>
    </tr>
  </tbody>
</table>
</div>




```python
# isnull() lê se algum campo está vazio
teste = pd.read_csv('TESTE.csv')
teste.isnull()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID;Nomes;Senhas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>False</td>
    </tr>
  </tbody>
</table>
</div>




```python
# na_values é um argumento que substitui valores ausentes na tabela
teste = pd.read_csv('teste2.csv', na_values=[5])
teste
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>1;</th>
      <th>Raphael</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2;</td>
      <td>Jhonathan</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3;</td>
      <td>Isabella</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4;</td>
      <td>João</td>
    </tr>
    <tr>
      <th>3</th>
      <td>5;</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# O read_xlsx lê arquivos de extensão xlsx() ou seja, Excel.
teste = pd.read_excel('teste3.xlsx')
teste
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>1</th>
      <th>Raphael</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>Jhonathan</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>Gabriel</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4</td>
      <td>Pedro</td>
    </tr>
    <tr>
      <th>3</th>
      <td>5</td>
      <td>Matheus</td>
    </tr>
    <tr>
      <th>4</th>
      <td>6</td>
      <td>Nathália</td>
    </tr>
    <tr>
      <th>5</th>
      <td>7</td>
      <td>Isabella</td>
    </tr>
    <tr>
      <th>6</th>
      <td>8</td>
      <td>Kaio</td>
    </tr>
    <tr>
      <th>7</th>
      <td>9</td>
      <td>Diego</td>
    </tr>
    <tr>
      <th>8</th>
      <td>10</td>
      <td>Fernando</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Vamos supor que você quer ler um arquivo todo, mas não quer lê-lo
#todo, o argumento nrows te ajuda nisso
teste = pd.read_excel('teste3.xlsx', nrows=5)
teste
# nrows=5 quer dizer que ele apenas lê as cinco primeiras linhas 
#do arquivo
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>1</th>
      <th>Raphael</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>Jhonathan</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>Gabriel</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4</td>
      <td>Pedro</td>
    </tr>
    <tr>
      <th>3</th>
      <td>5</td>
      <td>Matheus</td>
    </tr>
    <tr>
      <th>4</th>
      <td>6</td>
      <td>Nathália</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
