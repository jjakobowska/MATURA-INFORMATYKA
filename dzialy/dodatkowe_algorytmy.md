<h1 align="center"> Dodatkowe algorytmy </h1>

1. __algorytmy numeryczne__

   - [x] [Suma liczb od a do b](#suma)
   - [x] [Iloczyn liczb od a do b](#iloczyn)
   - [x] [Czy liczba jest parzysta](#even)
   - [x] [Czy liczba jest podzielna przez n bez reszty](#n)
   - [x] [Czy liczba jest wielokrotnością n](#multiple)
   - [ ] Najwiekszy i najmniejszy element w zbiorze
   - [ ] Moc liczby

2. __algorytmy arytmetyczne__

   - [x] [Silnia (n)](#factorial)
   - [x] [Pierwiastek kwadratowy](#sqrt)
   - [x] [Pierwiastek n-tego stopnia](#sqrt2)
   - [x] [Moda](#moda)
   - [x] [Mediana](#med)
   - [x] [Średnia arytmetyczna](#ary)
   - [x] [Średnia ważona](#waz)
   - [x] [Średnia geometryczna](#geo)
   - [x] [Wariancja i odchylenie standardowe](#odchylenie)
   - [ ] Symbol Newtona

3. __algorytmy na łańcuchach__  

   - [ ] Zliczanie znaków w ciągu
   - [ ] Zliczanie słów w łańcuchu
   - [ ] Wyszukiwanie najdłuższego słowa w łańcuchu
   - [ ] Wyszukiwanie najdłuższego wspólnego podłańcucha
   - [ ] Wyszukiwanie najdłuższego wspólnego podciągu
   - [x] [Krotność znaków w łańcuchu](#kro)
   - [ ] Naprzemienność dużych i małych liter w tekście
   - [ ] Algorytm Manachera	
   - [ ] Algorytm N 
   - [ ] Algorytm Knutha-Morrisa-Pratta
   - [ ] Algorytm Boyer-Moore'a
   - [ ] Algorytm Galila Seiferasa
   - [ ] Algorytm Karpa-Rabina

4. __kombinatoryka__
    
   - [ ] Porządek leksykograficzny
   - [ ] Wyszukiwanie liczby palindromów w tekście

5. __geometria__

   - [ ] Wyznaczenie punktów przecięcia okręgu z prostą
   - [ ] Wyznaczanie punktu przecięcia dwóch prostych
   - [ ] Przynależność punktu do odcinka
   - [ ] Przynależność punktu do wielokąta
   - [ ] Środek odcinka
   - [ ] Długość odcinka
   - [ ] Znajdowanie punktu tworzącego figure
   - [ ] Sprawdzanie czy proste są prostopadłe / równoległe

## Czy liczba jest parzysta [⬆️](#main)
<a name="even"></a>
<details><summary>Rozwiń</summary>

```python
def is_even(x):
   if x % 2 == 0:
      return True
   return False
```
</details>

## Czy liczba jest podzielna przez n bez reszty [⬆️](#main)
<a name="n"></a>
<details><summary>Rozwiń</summary>

```python
def divisible(x,n):
   if x % n == 0:
      return True
   return False
```
</details>

## Czy liczba jest wielokrotnością n [⬆️](#main)
<a name="multiple"></a>
<details><summary>Rozwiń</summary>

```python

def is_multiple2(x,n):
    if n % x == 0:
        return True
    return False

print(is_multiple(3,333))
```
</details>

## Silnia (n) [⬆️](#main)
<a name="factorial"></a>
<details><summary>Rozwiń</summary>

```python
from math import factorial

print(factorial(5))
```

```python
#Iterated version

def fact(n):
   factorial = 1
   if n >= 1:
      for i in range (1, n + 1):
         factorial = factorial * i
   return factorial
```

```python
#Recursive version

def fact(n):
   if n == 1:
      return n
   elif n < 1:
      return None
   return n*fact(n-1)
```
</details>

## Pierwiastek kwadratowy [⬆️](#main)
<a name="sqrt"></a>
<details><summary>Rozwiń</summary>

```python
from math import sqrt

print(sqrt(4))
```

```python
#sqrt1(number,stopien)

def sqrt1(x):
    return x ** (1/2)
```
</details>

## Pierwiastek n-tego stopnia [⬆️](#main)
<a name="sqrt2"></a>
<details><summary>Rozwiń</summary>

```python
#sqrt1(number,stopien)

def sqrt1(x,p):
    return x ** (1/p)
```
</details>

## Suma liczb od a do b [⬆️](#main)
<a name="suma"></a>
<details><summary>Rozwiń</summary>

```python
def suma(a,b):
    return sum(range(a, b + 1))
```

```python
def suma(a,b):
    wynik = 0
    for i in range(a, b +1 ):
        wynik += i
    return wynik
```
</details>

## Iloczyn liczb od a do b [⬆️](#main)
<a name="iloczyn"></a>
<details><summary>Rozwiń</summary>

```python
def iloczyn(a,b):
    wynik = 1
    for i in range(a, b + 1):
        wynik *= i
    return wynik
```
</details>

## Krotność np. znaków w ciągu [⬆️](#main)
<a name="kro"></a>
<details><summary>Rozwiń</summary>

```python
from collections import Counter

lista_slow = ['nie','zdam','matury']

lista_slow = ",".join(lista_slow)

print(Counter(lista_slow))
```

```python
def freq(str):
    dict = {}
    for n in str:
        keys = dict.keys()
        if n in keys:
            dict[n] += 1
        else:
            dict[n] = 1
    return dict

print(freq('slowo'))
```
</details>

## Moda/dominanta [⬆️](#main)
<a name="moda"></a>
<details><summary>Rozwiń</summary>

```python
from collections import Counter

lista=[1,2,3,4,5]

def moda(lista):
    if all(i == 1 for i in Counter(lista).values()):
        return lista
    return Counter(lista).most_common(1)[0][0]
 ```

```python
 def moda(lista):
    return max(set(lista), key = lista.count)
 ```
</details>

## Mediana [⬆️](#main)
<a name="med"></a>
<details><summary>Rozwiń</summary>

```python
def mediana(lista):
    for i in range(len(lista)):
        for j in range(len(lista) - i - 1):
            if lista[j] > lista[j + 1]:
                lista[j + 1], lista[j] = lista[j], lista[j + 1]

    if len(lista) % 2 == 0:
        mediana = lista[int(len(lista) / 2)] + lista[int(len(lista) / 2 - 1)]
        mediana /= 2
    else:
        mediana = lista[int(len(lista) / 2)]
    return mediana
 ```

 ### Ze wzoru:
![equation](https://raw.githubusercontent.com/wernexnrs123/MATURA-INFORMATYKA/master/dzialy/images/mediana.png)
</details>

## Średnia arytmetyczna [⬆️](#main)
<a name="ary"></a>
<details><summary>Rozwiń</summary>

```python
def srednia(x):
    return sum(x)/len(x)
 ```

```python
def srednia(x):
    count = 0
    licznik = 0
    for i in range(len(x)):
        count += 1
        licznik += x[i]
    return licznik/count
 ```

 ### Ze wzoru:
![equation](https://raw.githubusercontent.com/wernexnrs123/MATURA-INFORMATYKA/master/dzialy/images/srednia.png)
</details>

## Średnia ważona [⬆️](#main)
<a name="waz"></a>
<details><summary>Rozwiń</summary>

```python
def srednia(lista, wagi):
    wynik = sum((i * j for i, j in zip(lista, wagi))) / sum(wagi)
    return wynik

 ```

```python
def srednia(lista, wagi):
    wynik_wagi = 0
    wynik = 0
    for i in range(len(wagi)):
        wynik_wagi += wagi[i]
        wynik += lista[i] * wagi[i]
    return wynik/wynik_wagi

 ```

### Ze wzoru:
![equation](https://raw.githubusercontent.com/wernexnrs123/MATURA-INFORMATYKA/master/dzialy/images/srednia_wazona.png)
</details>

## Średnia geometryczna [⬆️](#main)
 <a name="geo"></a>
<details><summary>Rozwiń</summary>

```python
def srednia(lista):
    wynik = 1
    for i in lista:
        wynik *= i
    wynik = wynik ** (1/len(lista))
    return wynik
 ```

 ### Ze wzoru:
![equation](https://wikimedia.org/api/rest_v1/media/math/render/svg/d97e78adc3acddf0b54ed5624ab2ceff2057bf40)
</details>

## Wariancja i odchylenie standardowe [⬆️](#main)
<a name="odchylenie"></a>
<details><summary>Rozwiń</summary>

```python
def wariancja(lista):
    return sum(i ** 2 for i in lista) / len(lista) - (sum(lista) / len(lista)) ** 2
```

```python
def srednia(x):
    count = 0
    licznik = 0
    for i in range(len(x)):
        count += 1
        licznik += x[i]
    return licznik / count


def wariancja2(lista):
    n = 0
    suma = 0
    for i in range(len(lista)):
        n += 1
        suma += lista[i] ** 2
    return suma / n - srednia(lista) ** 2
```

### Ze wzoru:
![equation](https://raw.githubusercontent.com/wernexnrs123/MATURA-INFORMATYKA/master/dzialy/images/wariancja.png)
</details>
