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
     [[ 2.32746969 -0.81410502  1.12471392]
     [ 0.41214884  0.34083223 -0.44458745]
     [-1.98090165 -1.80182057  0.8891178 ]
     [-0.1698405  -0.66578559 -0.57135542]
     [ 0.22837541  2.26197848  0.40516571]]
    
    Matriz adulterada: 
     [[2.32746969 0.         1.12471392]
     [0.41214884 0.34083223 0.        ]
     [0.         0.         0.8891178 ]
     [0.         0.         0.        ]
     [0.22837541 2.26197848 0.40516571]]
    
    Verificando onde estão os elementos negativos: 
     [[False False False]
     [False False  True]
     [False False  True]
     [False  True  True]
     [ True False  True]]
    


```python
Matriz_Um = np.random.randn(5, 5)

X_Um = np.where((Matriz_Um < 0) | (Matriz_Um < 1), 1, Matriz_Um)
print(X_Um)
#Observe o uso do operador lógico OU no np.where( ), veja que para o uso de 
#expressões lógicas com operadores lógicos devemos colocar entre parênteses
#todos os itens o qual queremos trabalhar.
```

    [[1.         2.44939146 1.         1.00079269 1.        ]
     [1.14326355 1.         1.43105168 1.         1.        ]
     [1.         1.         1.         1.         1.        ]
     [1.         1.         1.32638609 1.         1.65259043]
     [1.         1.         1.         1.         1.        ]]
    

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

result
```

    [23 56]
    




    array([ 2,  2,  2,  2, -2])




```python
#Função reshape( )

x = np.arange(4, 4)

print(x.reshape)

print(x.T)

np.dot(x.T, x)

ArrayGigante = [3,4,6], [7,8,9], [10, 12,14]

#Função sqrt( ) e exp( )
np.sqrt(ArrayGigante)

np.exp(ArrayGigante)

#A função modf devolve a parte fracionária de um Array de ponto flutuante

testeFlut = np.array([5.01, 6.789, 6.45334])

print("Aqui", np.modf(testeFlut)) #Legal, página 209

```

    <built-in method reshape of numpy.ndarray object at 0x000002044284D4E0>
    []
    Aqui (array([0.01   , 0.789  , 0.45334]), array([5., 6., 6.]))
    


```python
impares = np.arange(10)

print(impares)

zero = np.zeros((2,4))

print(zero)
```

    [0 1 2 3 4 5 6 7 8 9]
    [[0. 0. 0. 0.]
     [0. 0. 0. 0.]]
    


```python
teste_UM = np.array([5, 7, 8], dtype = np.int64)

print(teste_UM.dtype)

floatCast = teste_UM.astype(np.float64)

print(floatCast.dtype)


```

    int64
    float64
    


```python
#Operações Aritméticas com os Arrays

data2 = [5, 6, 7]

array2 = np.array(data2)

array2 = array2 * 2

print(array2)
```

    [10 12 14]
    


```python
data3 = [8, 4, 6]

array3 = np.array(data3)

print(array3 > array2)
#Se for menor, True, senão, False.
```

    [False False False]
    


```python
#SliceNotation básico com os Arrays do NumPy

data4 = [5, 8, 3, 3, 2, 6, 7]

print(data4[2:6])
#Do segundo elemento até o sexto elemento do Array

print(data4[1: 3])
#Do primeiro até o segundo elemento do array

"""Página 190 do livro de Python para analise de dados"""

#Uma fatia vazia vai mostrar todos os elementos de um Array

data4[2] = 57

print(data4[:])
```

    [3, 3, 2, 6]
    [8, 3]
    [5, 8, 57, 3, 2, 6, 7]
    


```python
#Acessando um elemento de um Array bidimensional

data5 = np.array([[5, 7, 8], [4, 7, 8], [3, 6, 8]])

print(data5[2, 2])

#Como fatiar um Array Bidimensional??

print(data5[:1]) #Leia isso como, "Pegue a primeira linha de meu Array"

print(data5[0, : 2 ]) #Leia isso como: "Selecione a primeira linha(linha 0) mas somente as duas primeiras colunas"

print(data5[1, : 3])  #Leia isso como: "Selecione a segunda linha(linha 1) mas somente as três primeiras colunas"

print(data5[2, : 3])  #Leia isso como: "Selecione toda a terceira linha com suas colunas"

#De modo semelhante posso selecionar a coluna mas só algumas linhas, veja: Página 195 para ver as fatias para acessar índices

print("======================\n", data5[:3, 2]) #Selecionei as última coluna com todos os seus elementos(2), se fosse Um seria apenas dois elementos
```

    8
    [[5 7 8]]
    [5 7]
    [4 7 8]
    [3 6 8]
    ======================
     [8 8 8]
    


```python
data6 = np.array([5, 6, 7, 8])

data6[0 : 2] = 5 #Atribuição com o fatiamento

print(data6)
```

    [5 5 7 8]
    


```python
#Gerando dados aleatórios

data7 = np.random.randn(7, 4) # Sete linhas e quatro colunas

print(data7)

#Comparações Booleanas

data8 = np.array(["Bob", "Jonnhy", "Júlia"])

print(data8 == "Bob") #Dahora :D

#Para selecionar tudo, exceto o Bob, podemos usar o operador diferente( != )

print(data8 != "Bob")

#Podemos fazer comparações booleanas misturando o AND(&) e OR(|)

teste = (data8 == "Bob") & (data8 == "Júlia") #Observe que a comparação booleana foi armazenada em uma variável

```

    [[ 0.18499912  0.4874214  -0.68959549 -0.1290674 ]
     [ 1.35862785  1.04172398 -0.78669007 -0.32598415]
     [-0.11497671 -0.05426518  0.91129528 -1.88133248]
     [-0.43270067  1.56417956 -2.52606281  0.44626229]
     [ 0.4787379  -0.61916289  0.24998278 -1.20645292]
     [-0.24756329 -0.82615554 -1.47604846  1.2934423 ]
     [ 0.06821715 -0.55841096 -0.2735276  -0.8711915 ]]
    [ True False False]
    [False  True  True]
    


```python
#Estatística em NumPy (Página.217 e 218) (Página 220 para ver todas as funções de estatística para o NumPy)

data8 = [10, 20, 20, 26]

GOL = np.array(data8)

#Funções como SUM( ), MEAN( ), STD( ) realizam operações estatísticas nos Arrays

GOL.sum() #Soma todos os elementos de meu Array
GOL.mean() #Média aritmética de todos os elementos de meu Array
GOL.std()

GOL.cumsum() #A função cumsum() soma o primeiro elemento com o segundo, e o segundo com o terceiro, e ai por adiante

GOL.cumprod()
#Semelhante ao cumsum() a função cumprod() faz a multiplicação dos elementos de um Array, o primeiro vezes o segundo elemento, segundo
#vezes o terceiro, e assim por diante

GOL.max()#Retorna o maior valor do Array

```




    26




```python
#Arrays booleanos. Vamos usar duas funções para Arrays booleanos que testa se um ou mais de seus elementos são True ou False.

bools = np.array([True, False, True, False])

print("Um ou mais elementos são True: ", bools.any())

print("Todos os elementos de meu Array são True: ", bools.all())

#Essas funções funcionam com arrays de números, onde números maiores que segnifica True e 0 significa False

data9 = np.array([5, 6, 4, -1])

np.where(data9 > 0, "True", "False")

print(data9.any())
```

    Um ou mais elementos são True:  True
    Todos os elementos de meu Array são True:  False
    True
    


```python
#Ordenação de Arrays

GH = np.array([5, 7, 3, 2])
GH.sort() #Observe que sort() ordena os elementos do menor para o maior, uma função últil

print(GH)

data10 = np.random.randn(10)
print(data10)

data10.sort()

print(data10) #Certíssimo :)

#O np.unique() é uma função que não permite a redundância de elementos dentro de um Array

data11 = ([3, 3, 4, 4, 6, 6, 7, 7])
np.unique(data11)

#O np.in1d, realiza comparações de valores de um Array, caso os valores sejam igual ao elemento contido dentro do Array, será True, se não, False

data12 = np.array([50, 43, 6, 8, 6 ,9])
data13 = np.random.rand(15)

np.in1d(data12, 43, 50, 63)


```

    [2 3 5 7]
    [ 1.71800268  0.0811      0.33189548  0.05224959  0.32893614  0.57879489
      0.17439037  0.51566903 -0.74892344 -1.51228864]
    [-1.51228864 -0.74892344  0.05224959  0.0811      0.17439037  0.32893614
      0.33189548  0.51566903  0.57879489  1.71800268]
    




    array([ True, False,  True,  True,  True,  True])




```python
#Você também pode salvar seus Arrays em arquivos externos, sendo estes arquivos de dois tipos: binário e texto.

data14 = np.array([5, 7, 3, 6, 2, 4, 9])

np.save('Arquivo_teste', data14)

Arck = np.load('Arquivo_teste.npy')

print("Aqui está: ", Arck) # Sucesso
```

    Aqui está:  [5 7 3 6 2 4 9]
    


```python
data15 = np.array([5, 6, 4, 3])
data16 = np.array([5, 4, 3, 2])

np.dot(data15 ,data16)#O np.dot() realiza a múltiplicação de matrizes, onde cada elemento é multiplicado pelo elemento de outra matriz, em 
#seguida o resultado é somado( 5x 5) + (6 x 4) + (4 x 3) + (3 X 2) = 67

data15.dot(data16) # equivalente a np.dot() 

np.diag(data15)#Observe que a função diag() organizar os elementos de um Array na posição vertical
```




    array([[5, 0, 0, 0],
           [0, 6, 0, 0],
           [0, 0, 4, 0],
           [0, 0, 0, 3]])




```python
data18 = np.random.normal(size=(4, 4)) #Criei uma Matriz de 4 linhas e 4 colunas

print(data18)

#página 230 - 232 para ver sobre os atributos de random

```

    [[-1.76068717  1.20489915  0.37221618  0.30457522]
     [ 0.75032395 -0.48796775 -1.01844381  1.48870192]
     [-0.14240264 -0.43469764 -1.13620083  0.03814877]
     [-1.12540237 -3.47497635  0.89334145  0.26681695]]
    
