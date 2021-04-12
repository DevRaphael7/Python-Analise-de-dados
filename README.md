### **Python para Analise de dados**

Em Python temos três bibliotecas para analise de dados, e são:

- **Numpy**
- **Pandas**
- **Matplotlib**

## **1) Numpy**


O Numpy é uma biblioteca que nos permite programa com Arrays unidimensionais e multidimensionais, além de muitas outras funções para trabalhar com números decimais, geração de números aleatórios, etc...

Para usar a biblioteca Numpy devemos primeiro importar a biblioteca, fazemos isso usando a palavra reservada import, assim: 




```python
import numpy as np


```

O as é uma palavra reservada para atribuir um apelido a biblioteca.

Para criar um Array no Numpy primeiro crio uma variável, em seguida atribuo seus elementos dentro de colchetes, cada elemento é separado pela vírgula. Perceba que o Array(data1_Mu) abaixo tem dois grupos de elementos entre colchetes, esse Array é multidimensional por ter duas dimensões, é um Array unidimensional quando só há uma dimensão.



```python
#Array de uma dimensão
data1_Un = [2, 4, 6]

#Array de duas dimensões
data1_Mu = [2, 4, 6], [8, 10, 12]
```

## **Ndarray**
O ndarray é um dos principais recursos disponibilizado pela biblioteca Numpy que permite armazenar uma grande quantidade de dados em um só contêiner. O código abaixo nos mostra como criar um ndarray usando a função array( ) da biblioteca numpy. Observe que a função array( ) do numpy aceita qualquer tipo de código, incluindo outro array que deve ser colocado dentro de seu parâmetro:


```python
data1 = [2, 4, 6], [8, 10, 12]

pares = np.array(data1)

print(pares)

#Para criar um array diretamente na função array( ) é só usar os colchetes.
pares = np.array([14, 16])

print("\n", pares)


```

    [[ 2  4  6]
     [ 8 10 12]]
    
     [14 16]
    

As funções shape( ) e ndim( ) nos retorna o tamanho de um Array. Shape nos retorna o número de elementos deste Array e o número de dimensões, enquanto Ndim nos retorna apenas o número de dimensões(linhas).


```python
#Funções que retornam o tamanho dos Arrays
data2 = np.array([[3, 3, 3, 6], [4, 5, 6,7]])
#(Linhas, Colunas)
print(data2.shape)
#(Linhas)
print(data2.ndim)
```

    (2, 4)
    2
    

## Arrays com números aleatórios

A biblioteca numpy também nos permite criar conjunto de dados aleatórios. Para isso temos as funções: arange( ), zeros( ), ones( ), random.rand( ) e empty( ). O arange nos permite criar arrays unidimensionais, e valor colocado entre parêntes será a quantidade de elementos alocáveis dentre deste Array.


```python
#O zeros( ) e ones( ) criam arrays de 0 e 1
zeros_a = np.zeros(10)
print(zeros_a)

ones_a = np.ones(10)
print(ones_a)

#O empty( ) cria Array vazio, em alguns casos esses arrays não retornam
#zeros, mas o "lixo" não inicializados poderão ser devolvidos.

vazio = np.empty((10))
print(vazio)

#Com essas funções podemos criar arrays bidimensionais colocando mais de um
#argumento entre os parênteses

zeros_a = np.zeros((2, 3))
ones_a = np.ones((4, 4))
vazio = np.empty((4, 4, 2))
print("\n", zeros_a)
print("\n", ones_a)
print("\n", vazio)
```

    [0. 0. 0. 0. 0. 0. 0. 0. 0. 0.]
    [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
    [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
    
     [[0. 0. 0.]
     [0. 0. 0.]]
    
     [[1. 1. 1. 1.]
     [1. 1. 1. 1.]
     [1. 1. 1. 1.]
     [1. 1. 1. 1.]]
    
     [[[0. 0.]
      [0. 0.]
      [0. 0.]
      [0. 0.]]
    
     [[0. 0.]
      [0. 0.]
      [0. 0.]
      [0. 0.]]
    
     [[0. 0.]
      [0. 0.]
      [0. 0.]
      [0. 0.]]
    
     [[0. 0.]
      [0. 0.]
      [0. 0.]
      [0. 0.]]]
    

# **arange( )**


```python
#Unidimensional
aleatorio = np.arange(10)
print(aleatorio)

```

    [0 1 2 3 4 5 6 7 8 9]
    

## **Operações Aritméticas entre Arrays**

1)Multiplicar os Arrays por um número qualquer

2)Soma e subtração entre um Array e um número qualquer

3)Divisão de um Array por um número qualquer

4)Potenciação com array

5)Operações aritméticas entre mais de um Array


```python
data3  = np.array([5, 7, 8])

#Multiplicando meu Array por números inteiros

print("M:", data3 * 3) # Os elementos do array são todos multiplicados por três
print("M:", data3 * 5) # Os elementos do array são todos multiplicados por cinco

#Soma e Subtração de Arrays por números inteiros

print("\nA:", data3 + 4)# Os elementos do array são todos somados com quatro
print("S:", data3 + 4)# Os elementos do array são todos subtraídos por quatro

#Divisão de um Array por um número inteiro

print("\nD:", data3 / 2) #Os elementos do array são todos divididos por dois
print("D:", data3 / 5) #Os elementos do array são todos divididos por cinco

#Potenciação
print("\nExp:", data3 ** 2)#Array elevado ao quadrado
print("Exp:", data3 ** 3)#Array elevado ao cubo

#Operações com mais de um array

data4 = np.array([5, 6, 9])

print("\nSOMA:", data3 + data4)
print("SUBTRAÇÃO:", data3 - data4)
print("MULTIPLICAÇÃO:", data3 * data4)
print("DIVISÃO:", data3 / data4)

```

    M: [15 21 24]
    M: [25 35 40]
    
    A: [ 9 11 12]
    S: [ 9 11 12]
    
    D: [2.5 3.5 4. ]
    D: [1.  1.4 1.6]
    
    Exp: [25 49 64]
    Exp: [125 343 512]
    
    SOMA: [10 13 17]
    SUBTRAÇÃO: [ 0  1 -1]
    MULTIPLICAÇÃO: [25 42 72]
    DIVISÃO: [1.         1.16666667 0.88888889]
    

## **Comparações entre Arrays**

O uso de operadores relacionais com Arrays, resultam em valores booleanos como True e False. Claro que esses Arrays devem estar no mesmo tamanho. Observe que as comparações booleanas compara cada elemento entre ambos os Arrays, também é possível fazer esse procedimento com números naturais.

1)Comparações com números naturais

2)Comparações entre mais de um Array



```python
arr1 = np.array([5, 7, 8, 9]); arr2 = np.array([5, 3, 2, 9])

# -> (>) and (<)

print("arr1 > 5: ", arr1 > 5) #Compara cada elemento, retornando True e False
print("arr2 < 5: ", arr2 < 5)

# -> (==) and (!=)

print("\narr1 == 10", arr1 == 10)
print("arr2 != 10", arr2 != 5)
print("arr2 == 10", arr2 == 5)

# Comparações booleanas entre Arrays

print("\narr1 == arr2", arr1 == arr2)
print("arr1 != arr2", arr1 != arr2)
print("arr1 > arr2", arr1 > arr2)
print("arr1 < arr2", arr1 < arr2)
```

    arr1 > 5:  [False  True  True  True]
    arr2 < 5:  [False  True  True False]
    
    arr1 == 10 [False False False False]
    arr2 != 10 [False  True  True  True]
    arr2 == 10 [ True False False False]
    
    arr1 == arr2 [ True False False  True]
    arr1 != arr2 [False  True  True False]
    arr1 > arr2 [False  True  True False]
    arr1 < arr2 [False False False False]
    

## **Indexação entre Arrays e Fatiamento(Slice Notation)**

Em um alguns momentos vamos precisar fazer consulta em um Array, o problema é quando o Array é exteso e queros consultar apenas um subconjunto ou partes da aquele Array, em suma, quando queremos apenas acessar alguns dados e não todos. Um modo simples de fazer isso em Arrays unidimensionais é usando o slice(fatiamento):


```python
# ----> Índice

fatia_ex = np.array([14, 14, 15, 34, 56, 23, 46])

#Para acessar um elemento de um Array utilizo o seu índice
print(fatia_ex[0]) 
#Veja que obtive o primeiro elemento de meu array, o 14

# ----> Slice

#Um outro modo de fazer isso é usando o fatiamento, com ele obtemos mais de um elemento de uma só vez
print(fatia_ex[1:4])

#Observe que o primeiro argumento(1) é o elemento inicial onde vou começar a fatiar
#o segundo argumento é o índice final onde vou, até onde eu quero, fatiar

print("\nOs colchetes vazios [:] da fatia fará uma selecão geral de todo Array\n")
print(fatia_ex[:]) #Em numpy, o índice 0 é uma cópia do índice 1 logo:

print(fatia_ex[0:2])# Veja que o print( ) imprimiu dois Arrays

```

    14
    [14 15 34]
    
    Os colchetes vazios [:] da fatia fará uma selecão geral de todo Array
    
    [14 14 15 34 56 23 46]
    [14 14]
    

# Acessando linhas e elementos em um Array multidimensional


```python
#O primeiro argumento entre os colchetes é a linha, o segundo é a coluna, ou índice

arr_exMu = np.array([[5, 6, 7, 8], [12, 34, 5, 6]])

print("Ex.:", arr_exMu[1])#Acessando linha 1, que é a segunda linha

print("\nEx.:", arr_exMu[1, 2])#Acessando a linha 1 e o índice 3 do Array(R: 5)
```

    Ex.: [12 34  5  6]
    
    Ex.: 5
    

# Indexação com fatiamento

Obs.: 

a) Leia [:2] como "pegue as duas primeiras linhas da matriz por favor!";

b) Leia [:2, 1:] como, "pegue as duas primeiras linhas e as colunas a partir da primeira!", se tivesse colocado [:2, 1: 3] estaria dizendo para pegar as duas primeiras linhas e a coluna 1 até a coluna três.


```python
# Fatiando um array unidimensional

arr_slice = np.array([4, 6, 7, 8, 9])

print(arr_slice[0:3])

# Fatiar Array bidimensional

print("1)Selecionar linhas")

arr_slice = np.array([[5, 6, 7, 8], [1, 2, 3, 4], [3, 4, 5, 6]])

print("\n", arr_slice[:1]) #Observe que aqui estou selecionando a linha do meu Array
print("\n", arr_slice[:2])

print("\n2)Selecionar a linha e coluna")

print("\n", arr_slice[:2, 3:]) #Observe que aqui estou selecionando as duas primeiras linhas e a última coluna
print("\n", arr_slice[:2, 1:])
print("\n", arr_slice[:2, 1:3]) 
print("\n", arr_slice[:1, :1])#Selecionar a primeira linha e a primeira coluna 
print("\n", arr_slice[:1, 1:])#Selecionar a primeira linha e todas as colunas a partir da primeira
print("\n", arr_slice[:2, : 2])
print("\n", arr_slice[:2, 2: ])#Selecionar as duas primeiras linhas e ás últimas colunas
print("\n", arr_slice[:, 1:4])#Selecionando todas as linhas mas somente a coluna 1 até a 3

```

    [4 6 7]
    1)Selecionar linhas
    
     [[5 6 7 8]]
    
     [[5 6 7 8]
     [1 2 3 4]]
    
    2)Selecionar a linha e coluna
    
     [[8]
     [4]]
    
     [[6 7 8]
     [2 3 4]]
    
     [[6 7]
     [2 3]]
    
     [[5]]
    
     [[6 7 8]]
    
     [[5 6]
     [1 2]]
    
     [[7 8]
     [3 4]]
    
     [[6 7 8]
     [2 3 4]
     [4 5 6]]
    

## Indexação booleana

Em Numpy é possível fazer uma consulta booleana, por exemplo, imagine que eu tenho um array com nomes como Bob, Julia, Pedro, Thiago, etc... E quisesse buscar o Bob neste Array, posso perfeitamente utilizar o operador de comparação para isso(==), caso o nome Bob for encontrado, será True, senão False. (Obs.: palavras booleanas com AND e OR nunca funcionarão com Arrys booleanos, invés disso, usamos &(AND) e |(OR) em seus lugares).


```python
Nomes = np.array(['Bob', 'Júlia', 'João', 'Daniel', 'Pedro'])

print("Buscar Bob: ", Nomes == 'Bob')
print("Buscar Júlia: ", Nomes == 'Júlia') #Aqui sei que a júlia está no índice 1, pois o índice um está True.

#A indexação booleana não falahará se o array tiver o tamanho correto

#é possível selecionar tudo exceto 'Emma' em um Array com !=, veja:

Nomes_Two = np.array(['Emma', 'Ray', 'Norman', 'Phil', 'Isabella'])

print('Selecionando tudo menos Emma:', Nomes_Two != 'Emma') #Observe que a Emma está como False

#É possível estabelecer condições para selecionar um ou mais nomes em um Array com
#operadores lógicos, AND(&&) e OU(|)

data = (Nomes == 'Bob') & (Nomes_Two == 'Emma')

print("\n", data)

data = (Nomes == 'Daniel') & (Nomes_Two == 'Emma')

print("\n", data)

data = (Nomes == 'Daniel') & (Nomes_Two == 'Phil')

print("\n", data)

data = (Nomes == 'Daniel') | (Nomes_Two == 'Emma')

print("\n", data)

#Observe que quando o operador foi &(AND), só retornou True quando ambos elementos 
#pertencessem a índices iguais em seus respectivos Arrays

#Também é possível fazer atribuição com os operadores lógicos em um Array Booleano, veja:

Nomes_tree = np.array(['João', 'Maria', 'João', 'Pedro', 'Pedro'])

Nomes_tree[Nomes_tree != 'João'] = 5
print('\n', Nomes_tree) #Observe que todos os elementos diferentes de João foram substitídos por 5
```

    Buscar Bob:  [ True False False False False]
    Buscar Júlia:  [False  True False False False]
    Selecionando tudo menos Emma: [False  True  True  True  True]
    
     [ True False False False False]
    
     [False False False False False]
    
     [False False False  True False]
    
     [ True False False  True False]
    
     ['João' '5' 'João' '5' '5']
    

## Substituição de Elementos em Numpy

A substituição de um elemento pode ser feita através de uma condicional, ou seja, estabeleçemos condições para substituir um valor ou vários valores. Para isso usamos os colchetes [ expressão lógica ] nas variáveis ou Arrais.


```python
data_subs = np.array([-1, 2, 5, -6, 8])

#Veja acima que meu Array tem alguns elementos negativos, imagine a situação 
#onde queremos substituir todos os valores por 0, para fazer utilizamos uma
#expressão lógica.

data_subs[data_subs < 0] = 0 
#Leia isso como, se um elemento em data_subs for menor que zero, substitua por 0
print(data_subs)

data_subs[data_subs > 1] = 40
print(data_subs)

data_subs[data_subs == 40] = 5
print(data_subs)

data_subs[(data_subs > 1) & (data_subs < 6)] = 10
print(data_subs)

data_subs[(data_subs > 5) | (data_subs < 12)] = 14
print(data_subs)


```

    [0 2 5 0 8]
    [ 0 40 40  0 40]
    [0 5 5 0 5]
    [ 0 10 10  0 10]
    [14 14 14 14 14]
    

## Reshape


```python

data_teste = np.arange(32)
print("SEM RESHAPE( )\n", data_teste)


data_testeTwo = np.arange(32).reshape((8,4))
print("\nCOM RESHAPE( )\n", data_testeTwo)

#Observe que o RESHAPE( ) organiza, ou ordena, um dado array, veja que meu array tem 32
#elementos, então o reshape( ) ordenou 8 x 4, conforme escrito nos parâmetros

```

    SEM RESHAPE( )
     [ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23
     24 25 26 27 28 29 30 31]
    
    COM RESHAPE( )
     [[ 0  1  2  3]
     [ 4  5  6  7]
     [ 8  9 10 11]
     [12 13 14 15]
     [16 17 18 19]
     [20 21 22 23]
     [24 25 26 27]
     [28 29 30 31]]
    

## Transpose


```python
data_testeTree = np.arange(24).reshape((6, 4))

print(data_testeTree)

print('\n', data_testeTree.T)
#Observe que o TRANSPOSE, representado pela palavra reservada T, inverte a ordem
#linhas se tornam colunas e colunas se tornam linhas

data_testeTree = np.arange(16).reshape((8,2))

print('\n', data_testeTree)
print('\n', data_testeTree.T)
```

    [[ 0  1  2  3]
     [ 4  5  6  7]
     [ 8  9 10 11]
     [12 13 14 15]
     [16 17 18 19]
     [20 21 22 23]]
    
     [[ 0  4  8 12 16 20]
     [ 1  5  9 13 17 21]
     [ 2  6 10 14 18 22]
     [ 3  7 11 15 19 23]]
    
     [[ 0  1]
     [ 2  3]
     [ 4  5]
     [ 6  7]
     [ 8  9]
     [10 11]
     [12 13]
     [14 15]]
    
     [[ 0  2  4  6  8 10 12 14]
     [ 1  3  5  7  9 11 13 15]]
    

## Álgebra Linear em Numpy

As vezes pode ter situações que necessitam que somamos, multiplicamos, dividimos ou subtraímos duas matrizes, para isso usamos a função np.dot( ) 
da biblioteca Numpy de Python


```python
data_four = np.array([5, 6, 7]); data_five = np.array([7, 8, 9]);

print(np.dot(data_four, data_five))
#Veja que os elementos das matrizes foram multiplicados um pelo o outro

data_four = np.arange(10); data_five = np.arange(10)

#print('\n', np.dot(data_four, data_five))
#Os arrays não tem quantidade de linhas e colunas iguais
#portanto uma mensagem de erro será impressa

data_four = np.arange(10).reshape((2,5)); data_five = np.arange(10).reshape((5,2))

print('\n', np.dot(data_four, data_five))
#Observe que as matrizes não precisam ter quantidades de linhas e colunas iguais
#mas O NÚMERO DE ELEMENTOS IGUAIS 

```

    146
    
     [[ 60  70]
     [160 195]]
    

## Funções Universais

As funções universais, ou ufunc, são funções que realizam operações com todos
os elementos de um array, exemplos de ufuncs podemos citar sqrt( ) e exp( ):


```python
#Ufunc -> sqrt( )

para_teste = np.array([5, 7, 8, 9])

print('SQRT( ):\n', np.sqrt(para_teste))
#Calcula a raiz quadrada de cada elemento individualmente

#Ufunc -> exp( )

print('EXP():\n', np.exp(para_teste))
```

    SQRT( ):
     [2.23606798 2.64575131 2.82842712 3.        ]
    EXP():
     [ 148.4131591  1096.63315843 2980.95798704 8103.08392758]
    

Funções como sqrt( ) e exp( ) são chamadas de **funções unárias**, pois não necessitam de mais de uma matriz para realizar a sua tarefa. Outras como maximum, aceitam dois arrays, e por isso são chamadas de **funções binárias**, e então devolve apenas um array como resultado.


```python
#Ufunc -> maximum( )
para_teste = np.array([5, 6, 7])
para_testeTwo = np.array([3, 10, 6])

print(np.maximum(para_teste, para_testeTwo))
#A função MAXIMUM seleciona os elementos maiores em ambos os Arrays

#Ufunc -> modf( )
para_teste = np.array([5.56, 6.07, 7.45])
para_testeTwo = np.array([3.10, 10.45, 6.67])

print('\n', np.modf(para_teste))
print('\n', np.modf(para_testeTwo))
#A função modf( ) retorna a parte fracionária de um array de números de ponto 
#flutuante

#Ufunc -> abs( ) e fabs( )

para_teste = np.array([-10, -23.567, -5, 3.43632])
para_testeTwo = np.array([-5, -8, -9, -3.5])

print('\n', np.abs(para_teste))
print('\n', np.fabs(para_testeTwo))
#abs( ) e fabs( ) calculam o valor absoluto de uma matriz

#Ufunc -> square( )

para_teste = np.array([5, 13, 45, 6])
para_testeTwo = np.array([2, 4, 6, 8, 36])

print('\n', np.square(para_teste))
print('\n', np.square(para_testeTwo))
#A função square( ) calcula o quadrado de cada elemento de um Array,
#equivalente a para_teste ** 2

#Ufunc -> add( )

para_teste = np.array([10, 20, 30])
para_testeTwo = np.array([20, 40, 30])

print('\n', np.add(para_teste, para_testeTwo))
#A função add( ) soma os elementos do primeiro array com o segundo array

#Ufunc -> subtract( )

para_teste = np.array([20, 40, 60])
para_testeTwo = np.array([10, 20, 30])

print('\n', np.subtract(para_teste, para_testeTwo))

#Ufunc -> multiply( )

para_teste = np.array([5, 6, 7, 8])
para_testeTwo = np.array([5, 6, 7, 8])

print('\n', np.multiply(para_teste, para_testeTwo))
#A funcão multiply( ) multiplica os elementos de ambos os arrays

#Ufunc -> divide( )

para_teste = np.array([4, 6, 12, 25])
para_testeTwo = np.array([2, 3, 4, 5])

print('\n', np.divide(para_teste, para_testeTwo))
#A função divide( ) divide elementos de ambos os arrays

#Ufunc -> mod( )

para_teste = np.array([4, 35, 5, 14])
para_testeTwo = np.array([2, 5, 2, 7])

print('\n', np.mod(para_teste, para_testeTwo))
#Observe que o mod( ) nos retorna o resto de divisão, perceba que o 5 não é um 
#número par, mas ímpar, devido ao resto de divisão igual a 1
```

    [ 5 10  7]
    
     (array([0.56, 0.07, 0.45]), array([5., 6., 7.]))
    
     (array([0.1 , 0.45, 0.67]), array([ 3., 10.,  6.]))
    
     [10.      23.567    5.       3.43632]
    
     [5.  8.  9.  3.5]
    
     [  25  169 2025   36]
    
     [   4   16   36   64 1296]
    
     [30 60 60]
    
     [10 20 30]
    
     [25 36 49 64]
    
     [2. 2. 3. 5.]
    
     [0 0 1 0]
    

## np.meshgrid( )

A função np.meshgrid( ) da biblioteca Numpy aceita até dois Arrays 1D, e gerar duas novas matrizes 2D correspondentes a todos os pares(x ,y) nos dois arrays. Observe que meshigrid( ) tem dois argumentos, (x, y) sendo que o x é a quantidade de colunas, enquanto y é a quantidade de linhas.


```python
vetorOne = np.array([5, 4, 2])

vetorTwo = np.array([5, 4, 2])

x = np.meshgrid(vetorOne, vetorTwo)
print('\n', x)
#Duas matrizes 3x3

vetorOne = np.array([2, 2, 2])

vetorTwo = np.array([2, 2, 2])

x, y= np.meshgrid(vetorOne, vetorTwo)
print('\nX:', x, '\nY:', y)
#Observe que usar duas variáveis nos permite controlar melhor a matriz, 
#antes, ambas as matrizes 3 x 3 estavam juntas em uma única variável, deixando
#a visualização confusa e de mais difícil entendimento por parte do programador

vetorOne = np.array([4, 4, 4, 4])#Define a quantidade de colunas

vetorTwo = np.array([2, 2])#Define a quantidade de linhas

x, y= np.meshgrid(vetorOne, vetorTwo)
print('\nX:', x, '\nY:', y)
```

    
     [array([[5, 4, 2],
           [5, 4, 2],
           [5, 4, 2]]), array([[5, 5, 5],
           [4, 4, 4],
           [2, 2, 2]])]
    
    X: [[2 2 2]
     [2 2 2]
     [2 2 2]] 
    Y: [[2 2 2]
     [2 2 2]
     [2 2 2]]
    
    X: [[4 4 4 4]
     [4 4 4 4]] 
    Y: [[2 2 2 2]
     [2 2 2 2]]
    

## Expressões condicionais com Arrays **Numpy**

A função np.where( ) é um equivalente a if e else do Python puro. Veja abaixo um exemplo, onde estabeleço uma condição, M == 10, caso M for igual a 10, o valor será True portanto vai imprimir o elemento do array N, senão(else), imprimirá o elemento do Array M:


```python
M = np.array([10, 12, 13, 16, 18, 10])
N = np.array([2, 4, 5, 6, 7, 8])

print(np.where(M == 10, N, M))
#Se M == 10, imprime N, senão, imprime M

M = np.array([13, 11, 14, 17, 21, 56.6])
N = np.array([2, 4, 5, 6, 7, 8])

print('\n', np.where(np.mod(N, 2) == 0, M, N))
#Observe que estou usando função dentro de outra função, onde se o elemento
#dentro de N for PAR( resto de divisão igual a 0) ele imprimi o elemento no 
#array de M, senão N.

```

    [ 2 12 13 16 18  8]
    
     [13.  11.   5.  17.   7.  56.6]
    

Imagine a situação onde temos um array aleatório com X número de elementos, e quiséssemos substituir todos os valores negativos por zero, podemos realizar esta tarefa facilmente com np.where( ):


```python
Randomico = np.random.randn(5, 3)

print('\nMatriz original: \n', Randomico)

Negativos = np.where(Randomico < 0, 0, Randomico)

print('\nMatriz adulterada: \n', Negativos)
#Observe que todos os elementos negativos foram substituídos por zero.

Randomico = np.random.randn(5, 3)

#É possível verificar os elementos negativos com uma expresão que nos retorna 
#valores booleanos, True e False

print('\nVerificando onde estão os elementos negativos: \n', Randomico < 0)
```

    
    Matriz original: 
     [[-0.99079562  1.01181049  0.86401586]
     [-0.64406682  0.48386261 -0.69971868]
     [ 2.16843313  0.17246836 -1.25798021]
     [ 0.30799375 -1.46540739 -1.0959528 ]
     [-0.83963889  1.11747869 -0.89921753]]
    
    Matriz adulterada: 
     [[0.         1.01181049 0.86401586]
     [0.         0.48386261 0.        ]
     [2.16843313 0.17246836 0.        ]
     [0.30799375 0.         0.        ]
     [0.         1.11747869 0.        ]]
    
    Verificando onde estão os elementos negativos: 
     [[False False  True]
     [False  True  True]
     [False  True False]
     [ True  True False]
     [False  True  True]]
    


```python
Matriz_Um = np.random.randn(5, 5)

X_Um = np.where((Matriz_Um < 0) | (Matriz_Um < 1), 1, Matriz_Um)
print(X_Um)
#Observe o uso do operador lógico OU no np.where( ), veja que para o uso de 
#expressões lógicas com operadores lógicos devemos colocar entre parênteses
#todos os itens o qual queremos trabalhar.
```

    [[1.         1.25874674 1.         1.         1.        ]
     [1.         1.         1.         1.         1.        ]
     [1.27392644 1.         1.         1.08771556 1.        ]
     [1.         1.         1.         1.         1.13484655]
     [1.         1.         1.0537275  1.         1.        ]]
    

## **Funções de estatísticas e mateméticas para Analise de Dados**

Em Python temos algumas funções matemáticas que nos permite realizar cálculos estatíticos sobre dados. Exemplos são: sum( ), mean( ) e std( )(desvio padrão). Veja abaixo onde gero valores aleatórios para calcular estatística:


```python
SOMA_CONSECUTIVA = np.arange(10)

print('Array: ', SOMA_CONSECUTIVA, '\n')
print('Soma consecutiva dos elementos:', SOMA_CONSECUTIVA.sum())
```

    Array:  [0 1 2 3 4 5 6 7 8 9] 
    
    Soma consecutiva dos elementos: 45
    

Veja que o sum( ) realiza a soma consecutiva dos elementos de um array, e nos retorna o resultado da somatória.


```python
Media_Aritmetica = np.array([5, 5, 5, 5])
print('1)\n', Media_Aritmetica.mean())
# 5 + 5 + 5 + 5 = 20, QUE DIVIDIDO POR 4 É IGUAL A 2.0

Media_Aritmetica = np.array([3, 3, 3, 3])
print('2)\n', Media_Aritmetica.mean())
# 3 + 3 + 3 + 3 = 12, QUE DIVIDIDO POR 4 É IGUAL A 3.0

Media_Aritmetica = np.array([4, 4, 4, 4])
print('3)\n', Media_Aritmetica.mean())
# 4 + 4 + 4 + 4 = 16, QUE DIVIDIDO POR 4 É IGUAL A 4.0
```

    1)
     5.0
    2)
     3.0
    3)
     4.0
    

## Funções cumsum( ) e cumprod( )



```python
array_exemplo = np.array([10, 20, 30, 40])

print(array_exemplo.cumsum())

array_exemplo = np.array([2, 4, 8, 16])

print(array_exemplo.cumprod())
```

    [ 10  30  60 100]
    [   2    8   64 1024]
    

Observe que a função cumsum( ) e cumprod( ) tem finalidades semelhantes as funções sum( ) e prod( ), onde o 
primeiro faz a soma consecutiva dos elementos de um arrays, enquanto o segundo a multiplicação consecutiva.


```python
array_exemploDois = np.array([ 15, 15, 15, 15])

print("Soma: ", array_exemploDois.cumsum(), "\n")
print("Multiplicação: ", array_exemploDois.cumprod(), "\n")

```

    Soma:  [15 30 45 60] 
    
    Multiplicação:  [   15   225  3375 50625] 
    
    


```python
points = np.arange(-5, 5, 0.01)

xp, ys = np.meshgrid(points, points)

xp

#-----------------------------------

xppo = np.array([10,13,10,56,78])
yui = np.array([23,45,56,78,-90])

print(yui[(xppo == 10)])

#Veja que eu uso o [( )] para estabelecer uma condicional no meu Array

#O np.where estabelece uma condicional para as matrizes, ou seja, o seu objetivo é semelhante a um if( ) e else

result = np.where(yui > 0, 2, -2)

#Veja que a condicional é yui > 0, e o valor 2 é o argumento de caso a condicional seja atendida, se não, -2
#Todos os valores positivos serão 2, todos os negativos serão -2

```

    [23 56]
    

## **2) Pandas**

O Pandas é uma biblioteca de Python usada em conjunto com bibliotecas como Numpy, a diferença é que Numpy só trabalha com dados numéricos em comparação com o Pandas que trabalha com dados **heterogêneos**. Numpy só trabalha com arrays de dados numéricos homogêneo.

Para importar a biblioteca Pandas escreva:


```python
import pandas as pd
```

Talvez você ache mais fácil importar somente Series e Dataframe pelo seu uso frequente:


```python
from pandas import Series, DataFrame
```

Para começar é importante entender que o Pandas tem duas estruturas de dados consideradas principais da biblioteca: a **Series** e o **DataFrame**.

**a) Series**

A Series são arrays unidimensionais semelhante aos arrays de Numpy, a diferença é que esses Arrays são acompanhados de um outro arrays de dado numérico chamado de **índice**. Não entendeu? Veja um exemplo abaixo:


```python
array_um = pd.Series([5, 9.0, 10, 5, 6])

print(array_um)
```

    0     5.0
    1     9.0
    2    10.0
    3     5.0
    4     6.0
    dtype: float64
    

Observe que os dados inseridos na nossa Series está a **direita** da tela, o array de índice á **esquerda**, e veja que no final temos "dtype", este é o **metadado** da nossa Series.

Em Pandas podemos optar por escolher apenas os dados da nossa série e o range() do nosso índice, usamos os seguintes comandos para isso:

**Obs.:** o step é onde começa, o stop é onde termina meu array de índice.


```python
# Somente valores
print(array_um.values)

#Somente o índice
print(array_um.index)
```

    [ 5.  9. 10.  5.  6.]
    RangeIndex(start=0, stop=5, step=1)
    

Em uma Séries é possível "customizar" o nosso índice, ou seja, trocar números por letras ou palavras e vice-versa, usamos o seguinte comando:


```python
array_um = pd.Series([6, 9, 10, 23], index=['a', 'b', 'c', 'd'])
'''
    Observa que usamos o index, e index é um 
    parâmetro da Series para escolhermos qual
    será a representação de meu índice.
'''

print('Primeiro exemplo: \n{}'.format(array_um))

array_um = pd.Series([10, 3, 4, 6], index=['a', 'b', 'c', 'd'])


print('Segundo exemplo: \n{}'.format(array_um))
```

    Primeiro exemplo: 
    a     6
    b     9
    c    10
    d    23
    dtype: int64
    Segundo exemplo: 
    a    10
    b     3
    c     4
    d     6
    dtype: int64
    

Observe que no segundo exemplo eu apenas informei o primeiro índice mas não os índices seguintes, logo uma mensagem de erro será impressa.

## Acessando os elementos por meio do índice personalizado


```python
array_um = pd.Series([3, 5, 6], index=['k', 'j', 'l'])

print(array_um['k'])# Acessando três
print(array_um['j'])# Acessando cinco
print(array_um['l'])# Acessando seis
```

    3
    5
    6
    

## Atribuindo dados por meio de índice personalizado


```python
array_um['k'] = 5
print(array_um['k'])
array_um['j'] = 34
print(array_um['j'])
```

    5
    34
    

## Condicionais para Series em Pandas 

Assim como Numpy podemos estabelecer condicionais nos Arrays de Pandas:


```python
array_um = pd.Series([5, 6, 8, 10, 2, -2])
print('\n{}\n'.format(array_um))

'''
    Nesta condicional coloquei Array_um > 5, ou seja, só imprimirá 
    dados maiores que cinco
'''

print('\n{}\n'.format(array_um[array_um > 5]))

print('\n{}\n'.format(array_um[array_um < 0]))
```

    
    0     5
    1     6
    2     8
    3    10
    4     2
    5    -2
    dtype: int64
    
    
    1     6
    2     8
    3    10
    dtype: int64
    
    
    5   -2
    dtype: int64
    
    

## Operações aritméticas com Series


```python
array_um = pd.Series([10, 20, 30, 40])

print('Soma: \n{}\n'.format(array_um + 2))
print('Subtração: \n{}\n'.format(array_um - 4))
print('Multiplicação: \n{}\n'.format(array_um * 2))
print('Divisão: \n{}\n'.format(array_um / 2))

#É possível usar funções de Numpy com Pandas

np.square(array_um)
```

    Soma: 
    0    12
    1    22
    2    32
    3    42
    dtype: int64
    
    Subtração: 
    0     6
    1    16
    2    26
    3    36
    dtype: int64
    
    Multiplicação: 
    0    20
    1    40
    2    60
    3    80
    dtype: int64
    
    Divisão: 
    0     5.0
    1    10.0
    2    15.0
    3    20.0
    dtype: float64
    
    




    0     100
    1     400
    2     900
    3    1600
    dtype: int64



## Dicionários em Pandas

Em uma Series do Pandas, é possível passar um dicionário para um Array do Pandas, veja um exemplo:


```python
regiao = {
    'Pais': 'Brasil',
    'Estado': 'São Paulo',
    'Habitantes': 500000000
}

array_dicio = pd.Series(regiao)
print(array_dicio)
```

    Pais             Brasil
    Estado        São Paulo
    Habitantes    500000000
    dtype: object
    

Observe que ao colocar um dicionário no array do Pandas, não obtivemos um índice para cada dado, podemos ter um índice se inserimos um argumento no parâmetro do index


```python
number = ['Pais', 'Estado', 'Habitantes', 4, 5]

array_dc = pd.Series(regiao, index=number)
print(array_dc)
```

    Pais             Brasil
    Estado        São Paulo
    Habitantes    500000000
    4                   NaN
    5                   NaN
    dtype: object
    

**Observe.:** veja que o array faz uma busca na lista de **number**, veja que não foram encontrados o dado para o índice 4 e 5, então o resultado é **NaN**, que significa "Não a um Número", Not a Number. Para os índices encontrados o dado é mostrado normalmente.

## IsNull e NotNull em Pandas

A função isnull() detecta ausência de dados, e notnull os campos preenchidos com dados.


```python
numbers = ['Casa', 'Anfiltrião', 4, 1, 8, 1, 2, 3]
dicionario = {'Casa': 'Velha',
             'Anfiltrião':'João',
                 'Tv': 'Samsung'}
array_um = pd.Series(dicionario, index=numbers)

print('\n', pd.isnull(array_um))

print('\n', pd.notnull(array_um))
```

    
     Casa          False
    Anfiltrião    False
    4              True
    1              True
    8              True
    1              True
    2              True
    3              True
    dtype: bool
    
     Casa           True
    Anfiltrião     True
    4             False
    1             False
    8             False
    1             False
    2             False
    3             False
    dtype: bool
    


```python
array_um.isnull()
```




    Casa          False
    Anfiltrião    False
    4              True
    1              True
    8              True
    1              True
    2              True
    3              True
    dtype: bool




```python
array_um.notnull()
```




    Casa           True
    Anfiltrião     True
    4             False
    1             False
    8             False
    1             False
    2             False
    3             False
    dtype: bool



Em Pandas temos um atributo chamado de **name**, pense nele como um 'metadado' que diz o que é aquela tabela de dados


```python
dicionario_dois = {'K': 5, 'G':10}
array_geografia = pd.Series(['Brasil', 'EUA'])

array_geografia.name = 'Paises'
# Coloquei Paises

print(array_geografia)

# é possível inserir um "metadado" até para a minha lista de índices

array_geografia.index.name = 'Id  Paises'

array_geografia
```

    0    Brasil
    1       EUA
    Name: Paises, dtype: object
    




    Id  Paises
    0    Brasil
    1       EUA
    Name: Paises, dtype: object



Uma maneira mais limpa de atribuir índice de uma série é através de .index


```python
array_tr = pd.Series([10, 3, 5])

print(array_tr)

# Atributo index
array_tr.index = [1, 2, 3]

print(array_tr)

array_tr.index = ['a', 'b', 'c']

print(array_tr)
```

    0    10
    1     3
    2     5
    dtype: int64
    1    10
    2     3
    3     5
    dtype: int64
    a    10
    b     3
    c     5
    dtype: int64
    

### b) DataFrame

Um dataframe, como o próprio nome já diz, data quer dizer dados em português e frame quer dizer quadro em português, fazendo a junção dessas palavras temos: Quadro de dados. Um DataFrame representa uma tabela de dados retangular e contém uma coleção ordenadas de colunas, em que cada coluna tem um dado diferente(numérico, caractere, booleano, etc.). Os DataFrames assim como as Series tem um índice tanto para as linhas quanto para as colunas.

Existem muitas formas de se construir um DataFrame, as mais comuns são a partir de um dicionário, listas ou arrays de Numpy:


```python
dicio = {'Estado': ['São Paulo', 'Rio de Janeiro', 'Amazônia', 'Acre', 'Rondônia', 'Paraná'],
        'Habitantes': [10000, 20000, 30000, 600, 890, 133434]}

frame = pd.DataFrame(dicio)

frame
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
      <th>Estado</th>
      <th>Habitantes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>São Paulo</td>
      <td>10000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Rio de Janeiro</td>
      <td>20000</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Amazônia</td>
      <td>30000</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Acre</td>
      <td>600</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Rondônia</td>
      <td>890</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Paraná</td>
      <td>133434</td>
    </tr>
  </tbody>
</table>
</div>



Observe que através de um dicionário construimos a nossa primeira tabela de dados em Pandas. Veja que a sintaxe do código para fazer um quadro é:


```python
frame = pd.DataFrame()
```

Através da palavra reservada pd.DataFrame() construimos uma tabela.

Veja que o DataFrame tem seu índice atribuído automaticamente igual as Series.

## frame.head( )

O atributo head( ) realiza a mesma operação que pd.DataFrame(), mas ele só seleciona as primeira cinco linhas, veja o resultado abaixo:


```python
frame.head()
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
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>



## Sequência de colunas

É possível organizar as colunas em um DataFrame, ou melhor, a sequência de colunas.


```python
obito = {'Paises':['Brasil', 'EUA', 'Venezuela'],
         'Mortes':[330000, 40000, 344444]
        }
frame = pd.DataFrame(obito)
print(frame, '\n')

frame = pd.DataFrame(obito, columns=['Mortes','Paises'])
print(frame, '\n')

# Se você passar uma coluna que não existi, ela aparecerá com dados ausentes
#NaN = Not a Number

frame = pd.DataFrame(obito, columns=['Mortes','Paises', 'Cidade'])
print(frame)
```

          Paises  Mortes
    0     Brasil  330000
    1        EUA   40000
    2  Venezuela  344444 
    
       Mortes     Paises
    0  330000     Brasil
    1   40000        EUA
    2  344444  Venezuela 
    
       Mortes     Paises Cidade
    0  330000     Brasil    NaN
    1   40000        EUA    NaN
    2  344444  Venezuela    NaN
    

Assim como as Series é possível "customizar" o seu índice com o parâmetro index: 


```python
frame = pd.DataFrame(obito, columns=['Mortes','Paises'], index=[30, 29, 28])

print(frame)
```

        Mortes     Paises
    30  330000     Brasil
    29   40000        EUA
    28  344444  Venezuela
    

As colunas e linhas de um **DataFrame** também pode ser obtida através do nome da coluna entre colchetes e com o atributo loc( ), podemos obter a linha inserindo o seu índice entre parênteses:


```python
# Obtendo coluna
frame['Mortes']

print('\n')
'''
    Também é possível acessar a dados de uma coluna usando 
    a sintaxe: frame.Mortes ou frame.Pais,nomes sem aspas.
'''

print(frame.Mortes, '\n')
#OU
print(frame.Paises,'\n')

# Obtendo linha
frame.loc[30]
```

    
    
    30    330000
    29     40000
    28    344444
    Name: Mortes, dtype: int64 
    
    30       Brasil
    29          EUA
    28    Venezuela
    Name: Paises, dtype: object 
    
    




    Mortes    330000
    Paises    Brasil
    Name: 30, dtype: object



## Atribuindo uma nova coluna com ou não array de valores

- Inserir o nome da nova coluna entre colchetes
- Criar um vetor de igual quantidade de linhas para atribuir valores


```python
array_valor = [10, 20, 30]
frame['Nova_coluna'] = array_valor

print(frame)
```

        Mortes     Paises  Nova_coluna
    30  330000     Brasil           10
    29   40000        EUA           20
    28  344444  Venezuela           30
    

Agora usando Numpy


```python

array_valor = np.arange(1, 4)
frame['Nova_coluna_2'] = array_valor

print(frame)
```

        Mortes     Paises  Nova_coluna  Nova_coluna_2
    30  330000     Brasil           10              1
    29   40000        EUA           20              2
    28  344444  Venezuela           30              3
    

**Obs.:** quando você estiver atribuindo novos valores de um array, seja uma lista ou um array unidimensional de Numpy, não esqueça de que o tamanho deve ser igual ao DataFrame.


Como nos dicionários ou listas, a palavra reservada del( ) pode apagar colunas específicas de nossa Series e DataFrame.


```python
t = pd.Series([[10, 2, 5, 8], [23, 4, 6, 7]])

print(t)

#Forneça o índice da linha para apagar
del(t[0])

#Veja agora
print('\n', t)
```

    0    [10, 2, 5, 8]
    1    [23, 4, 6, 7]
    dtype: object
    
     1    [23, 4, 6, 7]
    dtype: object
    

Com os DataFrame


```python
dicionario = {'A': [23, 45],
             'B': [23, 67]}

t = pd.DataFrame(dicionario)

print(t.columns)

#Apagando a coluna A
del(t['A'])

#Veja o resultado
print(t.columns)
```

    Index(['A', 'B'], dtype='object')
    Index(['B'], dtype='object')
    

### Dicionarios aninhados em DataFrames

Quando atribuimos um dicionario aninhado ao nosso DataFrame, o Pandas interpreta as chaves como colunas, e as chaves internas( como Nome e Linha) como linhas. 

Quando um valor não for passado para a tabela retangular, o dado será NaN, ou seja, Not a Number.


```python
dicionario = {'Cliente':{'Nome':'Lucas', 'Senha':[1020, 780]},
             'Loja':{'Nome':['Delivery']}}

t = pd.DataFrame(dicionario)

t
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
      <th>Cliente</th>
      <th>Loja</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Nome</th>
      <td>Lucas</td>
      <td>[Delivery]</td>
    </tr>
    <tr>
      <th>Senha</th>
      <td>[1020, 780]</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



Abaixo temos a **transposição** do nosso DataFrame, ou seja, trocar linhas por colunas e colunas por linhas:


```python
t.T #o parâmetro .T é transposição.
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
      <th>Nome</th>
      <th>Senha</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Cliente</th>
      <td>Lucas</td>
      <td>[1020, 780]</td>
    </tr>
    <tr>
      <th>Loja</th>
      <td>[Delivery]</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



Matriz de Numpy para DataFrames


```python
matriz = np.array([[34, 56, 89], [67, 43, 12]])

t = pd.DataFrame(matriz, index=['Números','Senhas'])

t.values 
# Retorna somente os valores em formato de array bidimensional
```




    array([[34, 56, 89],
           [67, 43, 12]])



### Index

Os index são os rótulos ou metadados de uma linha de dados em um DataFrame

- .index para ver somente os índices
- pd.Index() para atribuir dados somentes a os rótulos


```python
array = pd.Series(np.arange(4), index=['a', 'b', 'c', 'd'])
print(array.index, '\n')

array_2 = pd.Index(np.arange(1, 11))
print(array_2)
```

    Index(['a', 'b', 'c', 'd'], dtype='object') 
    
    Int64Index([1, 2, 3, 4, 5, 6, 7, 8, 9, 10], dtype='int64')
    


```python
dicio = {'EUA':[233], 'Brasil':[344]}

t = pd.DataFrame(dicio, index=[25, 24])

25 in t.index
```




    True




```python
'EUA' in t.columns
```




    True



Um index em Pandas pode ser redundante:


```python
teste = pd.DataFrame(np.arange(4), index=[1, 2, 1, 2])

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
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
    </tr>
  </tbody>
</table>
</div>



### Métodos para Index

Os index do Pandas tem uma série de métodos que podem ser empregados, veja:

- **append( )** concatetena indexs

- **difference( )** mostra a diferença entre um index e outro.

- **union( )** calcula a união entre os index, retorna valores únicos sem redundância

- **unique( )**


```python
array_um = pd.Index([4, 5, 6, 7])

array_dois = pd.Index([5, 7, 8, 9])

array_um.append(array_dois)
```




    Int64Index([4, 5, 6, 7, 5, 7, 8, 9], dtype='int64')




```python
array_um.difference(array_dois)
```




    Int64Index([4, 6], dtype='int64')




```python
array_um.union(array_dois)
```




    Int64Index([4, 5, 6, 7, 8, 9], dtype='int64')




```python
array_um.unique() # dados sem redundância
```




    Int64Index([4, 5, 6, 7], dtype='int64')



### reindex()

O reindex criar um novo array de indices, veja um exemplo:


```python
array_teste = pd.Series([4, 6, 7], index=['b', 'c', 'a'])
array_teste
```




    b    4
    c    6
    a    7
    dtype: int64




```python
array_teste = array_teste.reindex(['a', 'b', 'c'])
array_teste
```




    a    7
    b    4
    c    6
    dtype: int64



Veja como o reindex organiza o nosso array de índice

### Estabelecendo o nome das colunas com columns

columns é um parâmetro que pode recerber um vetor como valor:


```python
array_teste = pd.DataFrame([34, 56, 10], index=[1, 2, 3], columns=['Pessoas'])
array_teste
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
      <th>Pessoas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>34</td>
    </tr>
    <tr>
      <th>2</th>
      <td>56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>10</td>
    </tr>
  </tbody>
</table>
</div>




```python
# observe que as colunas também podem ser alteradas
#com o parâmetro columns de reindex( )
array_teste = array_teste.reindex(columns=['Substituindo'])
array_teste
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
      <th>Substituindo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



### Descartando índices

Podemos usar a função drop( ) para retirar um índice, veja:


```python
array_teste = pd.Series(np.arange(11.), index=np.arange(11))

print(array_teste)
```

    0      0.0
    1      1.0
    2      2.0
    3      3.0
    4      4.0
    5      5.0
    6      6.0
    7      7.0
    8      8.0
    9      9.0
    10    10.0
    dtype: float64
    


```python
array_teste2 = array_teste.drop(1)
array_teste2
```




    0      0.0
    2      2.0
    3      3.0
    4      4.0
    5      5.0
    6      6.0
    7      7.0
    8      8.0
    9      9.0
    10    10.0
    dtype: float64




```python
array_teste2 = array_teste.drop([2, 4, 5])
array_teste2
```




    0      0.0
    1      1.0
    3      3.0
    6      6.0
    7      7.0
    8      8.0
    9      9.0
    10    10.0
    dtype: float64



### Indexação de arrays em Pandas


```python
array = pd.Series([2, 4, 6, 8, 10], index=['a', 'b', 'c', 'd', 'e'])

# Acessando pelo índice
print(array['a'])
print(array['b'])
print(array['c'])
print(array['d'])
print(array['e'])
```

    2
    4
    6
    8
    10
    


```python
array[0:]
```




    a     2
    b     4
    c     6
    d     8
    e    10
    dtype: int64




```python
array[1:]
```




    b     4
    c     6
    d     8
    e    10
    dtype: int64




```python
array[:]
```




    a     2
    b     4
    c     6
    d     8
    e    10
    dtype: int64




```python
array[1:2]
```




    b    4
    dtype: int64



### Filtragem com Series


```python
array[array > 4]
```




    c     6
    d     8
    e    10
    dtype: int64




```python
array[array != 2]
```




    b     4
    c     6
    d     8
    e    10
    dtype: int64



### Fatiamento com Series


```python
array['b':'d']
```




    b    4
    c    6
    d    8
    dtype: int64




```python
# Atribuindo valor com fatiamento.
array['a':'d'] = 5
array
```




    a     5
    b     5
    c     5
    d     5
    e    10
    dtype: int64



### Filtragem com DataFrame


```python
dicionario = {'Valor':[23, 45, 67], 'Numero':[23, 56, 31]}
array = pd.DataFrame(dicionario)
array
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
      <th>Valor</th>
      <th>Numero</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>23</td>
      <td>23</td>
    </tr>
    <tr>
      <th>1</th>
      <td>45</td>
      <td>56</td>
    </tr>
    <tr>
      <th>2</th>
      <td>67</td>
      <td>31</td>
    </tr>
  </tbody>
</table>
</div>




```python
array > 5
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
      <th>Valor</th>
      <th>Numero</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>True</td>
      <td>True</td>
    </tr>
    <tr>
      <th>1</th>
      <td>True</td>
      <td>True</td>
    </tr>
    <tr>
      <th>2</th>
      <td>True</td>
      <td>True</td>
    </tr>
  </tbody>
</table>
</div>




```python
array[array > 40] = 10
array
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
      <th>Valor</th>
      <th>Numero</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>23</td>
      <td>23</td>
    </tr>
    <tr>
      <th>1</th>
      <td>10</td>
      <td>10</td>
    </tr>
    <tr>
      <th>2</th>
      <td>10</td>
      <td>31</td>
    </tr>
  </tbody>
</table>
</div>



### loc e Iloc

Loc i iloc são operadores especiais do Pandas para indexação, com eles podemos selecionar um conjunto, grupo, de linhas e colunas de um DataFrame


```python
# Selecionando uma única linha
array.loc[0]
```




    Valor     23
    Numero    23
    Name: 0, dtype: int64




```python
# Selecionando um linha e colunas específicas
array.loc[0, ['Valor']]
```




    Valor    23
    Name: 0, dtype: int64



Veja que a sintaxe é:
    
   #### array.loc['Linha', ['Colunas']]


```python
array.iloc[0]
```




    Valor     23
    Numero    23
    Name: 0, dtype: int64




```python
array.iloc[0, [1]]
```




    Numero    23
    Name: 0, dtype: int64



Leia isso como "selecione a linha 0 e a coluna 1, que é a coluna Número"


```python
array.iloc[0, [0]]
```




    Valor    23
    Name: 0, dtype: int64




```python
# Selecionando as duas colunas
array.iloc[0, [0, 1]]
```




    Valor     23
    Numero    23
    Name: 0, dtype: int64



## Método matemáticos do Pandas

- add() ou radd para adição
- sub() ou rsub() para subtração
- div() ou rdiv() para divisão
- floordiv() o mesmo que //
- mul() ou rmul() para multiplicação
- pow() para potenciação


```python
s1 = pd.Series([2, 4, 5, 6])
s2 = pd.Series([2, 5, 8, 10])
```


```python
s1.add(s2)
```




    0     4
    1     9
    2    13
    3    16
    dtype: int64




```python
s1.sub(s2)
```




    0    0
    1   -1
    2   -3
    3   -4
    dtype: int64




```python
s1.div(s2)
```




    0    1.000
    1    0.800
    2    0.625
    3    0.600
    dtype: float64




```python
s1.floordiv(s2)
```




    0    1
    1    0
    2    0
    3    0
    dtype: int64




```python
s1.mul(s2)
```




    0     4
    1    20
    2    40
    3    60
    dtype: int64




```python
s1.pow(s2)
```




    0           4
    1        1024
    2      390625
    3    60466176
    dtype: int64



### Ordenação e classificação

Podemos organizar os dados de nossa Series de acordo com critérios que estabelecemos.

Por exemplo, ordenar os índice em ordem alfabética ou crescente:


```python
array = pd.Series([98, 23, 45, 56], index=[4, 3, 6, 5])
array.sort_index()
```




    3    23
    4    98
    5    56
    6    45
    dtype: int64




```python
array = pd.Series([23, 450, 96, 122], index=[23, 22, 21, 20])
array.sort_index()
```




    20    122
    21     96
    22    450
    23     23
    dtype: int64



Podemos ordenar também um DataFrame.


```python
frame = pd.DataFrame(np.arange(12).reshape(3, 4), index=[4, 2, 3])
frame.sort_index()
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
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>4</td>
      <td>5</td>
      <td>6</td>
      <td>7</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8</td>
      <td>9</td>
      <td>10</td>
      <td>11</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
</div>



O parâmetro Axis ordena de maneira crescente os dados dentro de uma coluna, e não do array de índices:


```python
frame.sort_index(axis=1)
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
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4</td>
      <td>5</td>
      <td>6</td>
      <td>7</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8</td>
      <td>9</td>
      <td>10</td>
      <td>11</td>
    </tr>
  </tbody>
</table>
</div>



Os dados são ordenados em ordem crescente por padrão, mas podem ser ordenados de forma descrecente se inserimos o parâmetro Axis dentro dos parênteses:


```python
frame.sort_index(ascending=False)
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
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8</td>
      <td>9</td>
      <td>10</td>
      <td>11</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4</td>
      <td>5</td>
      <td>6</td>
      <td>7</td>
    </tr>
  </tbody>
</table>
</div>



Funciona com as Series também:


```python
array.sort_index(ascending=False)
```




    23     23
    22    450
    21     96
    20    122
    dtype: int64



Para ordenar uma Series de acordo com seus valores, utilizamos sort_values():


```python
#Valores em ordem crescente
array.sort_values()
```




    23     23
    21     96
    20    122
    22    450
    dtype: int64




```python
array = pd.Series([2, 3, -1, 0, 5], index=['a', 'b', 'c', 'd', 'c'])
array.sort_values()
```




    c   -1
    d    0
    a    2
    b    3
    c    5
    dtype: int64



Em ordem descrecente inserimos o parâmetro ascending igual a sort_index( )


```python
array.sort_values(ascending=False)
```




    c    5
    b    3
    a    2
    d    0
    c   -1
    dtype: int64



Assim como em uma consulta a um banco de dados, você pode ordenar de acordo com dados de uma coluna específica de um dicionário. Para isso usamos o argumento by de sort_values( )


```python
dicionario = {'a':[23, 67, 45], 'c':[67, 34, 1], 'b':[45, 80, 70]}
frame = pd.DataFrame(dicionario)
```


```python
frame.sort_values(by='a')
# Veja que a coluna a está ordenada de maneira crescente mas
# a coluna c e b não
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
      <th>a</th>
      <th>c</th>
      <th>b</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>23</td>
      <td>67</td>
      <td>45</td>
    </tr>
    <tr>
      <th>2</th>
      <td>45</td>
      <td>1</td>
      <td>70</td>
    </tr>
    <tr>
      <th>1</th>
      <td>67</td>
      <td>34</td>
      <td>80</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame.sort_values(by=['a', 'b'])
#a e b estão ordenadas
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
      <th>a</th>
      <th>c</th>
      <th>b</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>23</td>
      <td>67</td>
      <td>45</td>
    </tr>
    <tr>
      <th>2</th>
      <td>45</td>
      <td>1</td>
      <td>70</td>
    </tr>
    <tr>
      <th>1</th>
      <td>67</td>
      <td>34</td>
      <td>80</td>
    </tr>
  </tbody>
</table>
</div>



### Indexação duplicada

Em Pandas, quando indexamos manualmente nossa Series, não é obrigatório inserir valores únicos no índice ficando valores redundantes, veja um exemplo de redundãncia:


```python
array = pd.Series([23, 45, 60, 90], index=['a', 'b', 'b', 'c'])
array
```




    a    23
    b    45
    b    60
    c    90
    dtype: int64



a propriedade is_unique diz se sua Serie é única ou não, se sim, retorna True, se não, False


```python
array.is_unique
```




    True



### Métodos estatísticos para DataFrame

Assim como Numpy em Pandas podemos usar funções como SUM(), MEAN() para cálculos estatísticos de nossos dados.


```python
dicio = {'Um':[20, 34], 'Dois':[5, 6], 'Três':[120, 90]}
frame = pd.DataFrame(dicio)
frame
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
      <th>Um</th>
      <th>Dois</th>
      <th>Três</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>20</td>
      <td>5</td>
      <td>120</td>
    </tr>
    <tr>
      <th>1</th>
      <td>34</td>
      <td>6</td>
      <td>90</td>
    </tr>
  </tbody>
</table>
</div>




```python
# SUM() = soma consecutiva
frame.sum()
```




    Um       54
    Dois     11
    Três    210
    dtype: int64




```python
#MEAN() = Média Aritmética
frame.mean()
```




    Um       27.0
    Dois      5.5
    Três    105.0
    dtype: float64




```python
# O idxmax() retorna o índice da linha do maior valor
frame.idxmax()
```




    Um      1
    Dois    1
    Três    0
    dtype: int64




```python
# O idxmin() retorna o índice da linha do menor valor
frame.idxmin()
```




    Um      0
    Dois    0
    Três    1
    dtype: int64




```python
#Soma os dados em todas as linhas
frame.cumsum()
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
      <th>Um</th>
      <th>Dois</th>
      <th>Três</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>20</td>
      <td>5</td>
      <td>120</td>
    </tr>
    <tr>
      <th>1</th>
      <td>54</td>
      <td>11</td>
      <td>210</td>
    </tr>
  </tbody>
</table>
</div>



.describe() nos retorna uma série de dados estatísticos de uma só vez


```python
frame.describe()
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
      <th>Um</th>
      <th>Dois</th>
      <th>Três</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>27.000000</td>
      <td>5.500000</td>
      <td>105.000000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>9.899495</td>
      <td>0.707107</td>
      <td>21.213203</td>
    </tr>
    <tr>
      <th>min</th>
      <td>20.000000</td>
      <td>5.000000</td>
      <td>90.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>23.500000</td>
      <td>5.250000</td>
      <td>97.500000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>27.000000</td>
      <td>5.500000</td>
      <td>105.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>30.500000</td>
      <td>5.750000</td>
      <td>112.500000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>34.000000</td>
      <td>6.000000</td>
      <td>120.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# max() retorna o valor máximo de uma coluna
frame.max()
```




    Um       34
    Dois      6
    Três    120
    dtype: int64




```python
# min() retorna o valor mínimo de uma coluna
frame.min()
```




    Um      20
    Dois     5
    Três    90
    dtype: int64



### Ordenação de Series

É possível ordenar uma séries com o values_counts(sort=True ou False).

Obs.: a coluna de dados troca com a coluna de índice


```python
pan = pd.Series(np.arange(14))
pan.value_counts(sort=False)
```




    0     1
    1     1
    2     1
    3     1
    4     1
    5     1
    6     1
    7     1
    8     1
    9     1
    10    1
    11    1
    12    1
    13    1
    dtype: int64




```python
pan.value_counts(sort=True)
```




    13    1
    12    1
    11    1
    10    1
    9     1
    8     1
    7     1
    6     1
    5     1
    4     1
    3     1
    2     1
    1     1
    0     1
    dtype: int64



### isin()

isin() verifica um array vendo em qual posição se encontra o valor informado no parâmetro


```python
pan.isin([10, 2])
```




    0     False
    1     False
    2      True
    3     False
    4     False
    5     False
    6     False
    7     False
    8     False
    9     False
    10     True
    11    False
    12    False
    13    False
    dtype: bool




```python
pan = pd.Series([23, 56, 32, 23, 45])
pan.isin([23])
```




    0     True
    1    False
    2    False
    3     True
    4    False
    dtype: bool




```python

```
