## Zapis zmiennopozycyjny

Składa się z bitów:
- znak (S): określna czy liczba jest dodatnia czy ujemna
- mantysa (M): cyfry znaczące
- cecha (C): określa przesunięcie przecinka (w lewo lub w prawo)

Wtedy taka liczba to $(-1)^S * M * 2^C$

Dodatnia liczba rzeczywista ma skończone rozwinięcie dwójkowe wtw jest postaci $\frac{m}{2^n}$

## Uwarunkowanie zadania

Żeby sprawdzić czy zadanie jest dobrze uwarunkowane należy wyliczyć wskaźnik uwarunkowania zadania:

$cond(f, x) = |\frac{x * f'(x)}{f(x)}|$

Pokazuje to jak błąd względy danych wejściowych wpływa na bląd względny wyjścia. Jeżeli wskaźnik jest równy około $1$a, to zadanie jest dobrze uwarunkowanego, jeżeli jest wysoki to źle.

Jeżeli zadanie ma wiele parametrów wejściowych, należy sprawdzić każdy z nich osobno, trafktując pozostałe paramtery jako stałe podczas obliczania pochodnych.

## Zadanie dobrze zdefiniowane

Zadanie jest dobrze zdefiniowane w sensie Hadamarda jeżeli:
1. Istnienie rozwiązania: Dla dowolnych dopuszczalnych danych wejściowych istnieje rozwiązanie zadania
2. Jednoznaczność rozwiązania: Rozwiązanie to jest unikalne (istnieje dokładnie jedno).
3. Ciągła zależność od danych: Rozwiązanie zależy w sposób ciągły od danych wejściowych (stabilność). Oznacza to, że małe zmiany w danych początkowych (lub parametrach) prowadzą do proporcjonalnie małych zmian w wyniku, bez gwałtownych skoków.

Żeby sprawdzić warunek 3. sprawdzamy czy istnieje stała Lipschitza:

$| \phi(d_1) - \phi(d_2) | \le L * | d_1 - d_2 | $

Czyli czy da się ograniczyć skończoną liczbą róźnice na danych wyjściowych.

## Utrata cyfr znaczących

Podczas odejmowania dwóch bardzo bliskich sobie liczb (różniących się od siebie o $\epsilon$) ich cyfry znaczące zredukują się i zostanie sam $\epsilon$, który może być poza zakresem dokładności, co spowoduje, że taka różnica będzie równa $0$.

Wykonując kolejne obliczenia, które zamiast bardzo małej liczby uwględnią $0$, może dojść do całkowitej zmiany ostatecznego wyniku.

## Rozwinięcia w szereg Taylora

$sin(x) = \sum_{n=0}^{\infty}{\frac{(-1)^nx^{2n+1}}{(2n+1)!}}$

$cos(x) = \sum_{n=0}^{\infty}{\frac{(-1)^nx^{2n}}{(2n)!}}$

Albo:

$sin(x) = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \dots$

$cos(x) = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \dots$

