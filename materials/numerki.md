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

## Utrata cyfr znaczących

Podczas odejmowania dwóch bardzo bliskich sobie liczb (różniących się od siebie o $\epsilon$) ich cyfry znaczące zredukują się i zostanie sam $\epsilon$, który może być poza zakresem dokładności, co spowoduje, że taka różnica będzie równa $0$.

Wykonując kolejne obliczenia, które zamiast bardzo małej liczby uwględnią $0$, może dojść do całkowitej zmiany ostatecznego wyniku.

## Rozwinięcia w szereg Taylora

$sin(x) = \sum_{n=0}^{\infty}{\frac{(-1)^nx^{2n+1}}{(2n+1)!}}$

$cos(x) = \sum_{n=0}^{\infty}{\frac{(-1)^nx^{2n}}{(2n)!}}$

Albo:

$sin(x) = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \dots$

$cos(x) = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \dots$

## Wielomiany Czebyszewa

$T_0(x) = 1$

$T_1(x) = x$

$T_k(x) = 2x * T_{k-1}(x) - T_{k-2}(x)$

Własności:

$T_{m * n}(x) = T_m(T_n(x))$

## Aproksymacja średniokwadratowa

Polega na znalezieniu funkcji która możliwie nalepiej odwzorowuje poczynione obserwacje, poprzez wyznaczenie funkcji błędu zależnej od ustalanego parametru i obliczeniu minimum takiej funkcji.

Niech $C(t)$ to szukany model z parametrem $A$ , a $(t_k, C_k)$ to obserwacje:

$S(A) = \sum_{k=0}^{n}(C_k - C(t_k))^2$

Musimy obliczyć dla jakiego $A$ zachodzi $S'(A) = 0$

Parametrów może być więcej, wtedy obliczamy analogicznie, ale zerując pochodne cząstkowe po każdym parametrze.

## NIFS 3

To funkcja przybliżająca jakąś inną funkcje za pomocą sklejonych ze sobą (w węzłach) wielomianów 3 stopnia.

Węzły to wyznaczone punkty dla których wartości NIFS3 oraz przybliżanej funkcji są identyczne.

Muszą spełniać warunki:
- przedziałami (pomiędzy węzłami) jest wielomianem co najwyżej 3 stopnia
- $s(x_k) = y_k$ (odpowiada wartościom w węzłach)
- $s, s', s''$ są ciągłe
- $s''(a) = s''(b) = 0$ (globalne końce przedziałów mają zerową drugą pochodną)

## Rozkład LU i metoda faktoryzacji

Metoda faktoryzacji polega na rozbiciu macierzy na LU (Lower i Upper) czyli iloczyn macierzy dolnotrójkątnej z jedynami na przekątnej oraz górnotrójkątnej.

Odbywa się to poprzez stworzenie macierzy $Id * A$ i robienie jednocześnie eliminacji Gaussa obu macierzach, nie zmieniając kolejności wierszy, co ostatecznie prowadzi do uzyskania rozkładu LU.

Taki rozkład można wykorzystach do rozwiązania w czasie $O(n^2)$ układu równań liniowych $A\vec{x}=\vec{b}$. Przy czym należy pamiętać, że sama faktoryzacji pozwalająca uzyskać rozkład LU ma złożonośc $O(n^3)$.

Trik wygląda następująco:

$A\vec{x}=\vec{b}$

$LU\vec{x}=\vec{b}$

Podstawiamy:

$\vec{y} = U\vec{x}$

$L\vec{y} = \vec{b}$ (Podstawienie "w przód", rozwiązujemy to i dostajemy $\vec{y}$)

$\vec{y} = U\vec{x}$ (Teraz podstawiamy "w tył" otrzymany $\vec{y}$ i obliczamy $\vec{x}$)

Czyli zamiast rozwiązywać jednen trudny układ równań $O(n^3)$ rozwiązujemy dwa układy trójkątne, czyli proste w $O(n^2)$. 

## Złożony wzór trapezów

## Przybliżanie rozwiązania układu równań nieliniowych

## Metoda bisekcji

