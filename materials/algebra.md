## Kombinacje liniowe

Kombinacja liniowa to wektor powstały przez sumowanie ustalonych wektorów pomnożonych przez skalary.

$\vec{x} = a_1 * \vec{v_1} + ... + a_n * \vec{v_n}$

Wektory te mogą pochodzić z jakiejś bazy.

## Przeształcenie liniowe

Funkcja jest przeształceniem liniowym jeżeli spełnia:
- $F(\alpha \vec{v}) = \alpha F(\vec{v})$
- $F(\vec{v} + \vec{w}) = F(\vec{v}) + F(\vec{w})$

## Wektory zależne

Wektor jest zależy wtw kiedy można wyrazić go kombinację liniową innych wektorów z danego układu.

Wektory są niezależne jeżeli spełniona jest implikacja:

$\sum^{k}_{i=1}\alpha_i\vec{v}_i = 0 \implies a_1 = ... = a_k = 0$

## Wyznaczniki macierzy

Wyznacznik macierzy $A$ oznaczamy $|A|$ i oznacza on współczynik zmiany objętości obszaru na który działa przekształcenie liniowe (nasza macierz).

W szczególności jeżeli wyznacznik jest równo $0$ to obszar ulega "zapadnięciu" (zeruje objętość obszaru). Mówiąć inaczej tracimy informacje o jakimś wymiarze.

Wyznacznik ujemny oznacza zmianę objętności przy jednoczesnym "wywrócenie na drugą stronę" obszaru.

Dla macierzy trójkątnych (zarówno górnych jak i dolnych) wyznacznik macierzy to iloczyn elementów na przekątnej.

Inne własności:
- $|A * B| = |A| * |B|$
- $|A| = |A^T|$
- $|A^{-1}| = \frac{1}{|A|}$

## Obraz, jądro, baza i rząd macierzy

Obraz macierzy to zbiór wszystkich wyników mnożenia macierzy przez dowolne wektory.

Jądro macierzy to zbiór wektorów, które przekształcone przez macierz dają wektor $\vec{0}$. Oznaczamy jako $ker(A)$.

Rząd macierzy to liczba niezależnych kolumn w tej macierzy (wymiar obrazu macierzy). Oznaczamy to jako $r(A)$.

Baza to zbiór niezależnych wektorów, które są wystarczające do rozpięcia danej przestrzeni.

Ponadto $dim(ker(A)) + r(A) = dim(A)$

## Znajdowanie bazy jądra

1. Eliminacja Gausa po wierszach
2. Wyznaczenie wyrazów wolnych (tam gdzie nie ma schodka po eliminacji)
3. Zapisanie wierszy macierzy w formie rownań
4. Wyznaczanie zależności pomiędzy zmiennymi (mają być zależne od wyrazów wolnych)
5. Wyznaczenie wektorów (każdy wektor odpowiada jedenej zmiennej wolnej, a jego współczyniki to współczyniki zależy w stosunku do innych zmiennych)

## Znajdowanie bazy obrazu

1. Eliminacja Gausa po kolumnach do postaci schodkowej.
2. Bierzemy do bazy wszystkie wektory, które się nie zredukują do $\vec{0}$.

## Macierz odwrotna

Macierz odwrotna do jakiejś macierzy to taka która po przemnożeniu przez nią daje macierz indetycznościową.

$M * M^{-1} = M^{-1} * M = I$

Ponadto:

- $(M^T)^{-1} = (M^{-1})^T$
- $(M^{-1})^{-1} = M$
- $(MN)^{-1} = N^{-1} M^{-1}$

Macierz $n \times n$ jest odwracalna wtw jej rząd to $n$.

## Wartości i wektory własne

Macierz ma wektor własny $\vec{x}$ i odpowiadającą mu wartość własną $\lambda$ wtw:

$A\vec{x} = \lambda \vec{x}$

Intuicyjnie macierz $A$ zachowuje się jak skalar $\lambda$ dla wektora $\vec{x}$.

$A\vec{x} = \lambda \vec{x} \iff |A - \lambda I|\vec{x} = 0 \iff |A - \lambda I| = 0$

Czyli $\lambda$ jest wartością własną macierzy wtw $|A - \lambda I| = 0$

Istnieje powiązanie:

$|A| = \Pi_{i=1}^{n} \lambda_i$

## Wielomian charakterystyczny

Jest to "spakowana" wersja wszystkich wartości własnych macierzy na raz w formie wielomianu.

$p_A(\lambda) = |A - \lambda I|$

## Krotności algebraiczne i geometryczne

Krotność algebraiczna wartości własnej to liczba jej wystąpień jako rozwiązanie wielomianu charakterystycznego.

Krotność geometryczna wartości własnej to liczba niezależnych wektorów własnych odpowiadających tej wartości własnej.

## Macierz dodatnio określona

Żeby sprawdzić czy macierz jest dodatnio określona można wykorzystać dowolony ze sposobów:
- kryterium Sylvestera (wszystkie wyznaczniki kolejnych lewych górnych kwadratowych podmacierzy są dodatnie)
- ma wszystkie wartości własne dodatnie

## Czy układ równań ma rozwiązanie

Niech układ równań ma postać $AX = B$

Niech $U = [A|B]$

Układ równań ma rozwiązanie wtw $r(A) = r(U)$.

Jeśli:
- $r(A) = r(U) = n$ ($n$ to liczba niewiadomych) to układ ma dokładnie jedno rozwiązanie
- $r(A) = r(U) = x < n$ to układ ma nieskończenie wiele rozwiązań zależnych od $n - x$ parametrów (jeżeli rozwiązujemy je w ciele skończonym to wtedy liczba rozwiązań to liczba elementów ciała podniesiona do potęgi równej liczbie parametrów).
- $r(A) < r(U)$ to układ jest sprzeczny

## Macierze ortogonalne

Macierz jest ortogonalna jeżeli $A^TA = I$

Ponadto macierz jest ortogonalna wtw $A^T = A^{-1}$

## Rozwinięcie Laplace

Wybieramy jakiś i-ty wiersz (lub kolumnę), najlepiej taki który ma w sobie dużo $0$.

$|A| = \sum_{j=1}^n a_{i,j} * (-1)^{i + j} * |A^{(i,j)}|$

Gdzie $A^{(i,j)}$ to podmacierz $A$ z wykreślonymi i-tym wierszem i j-tą kolumną.

Wzór można powtarzać rekurencyjnie.

## Iloczyn skalarny

Jakie właściwości musi spełniać przekształcenie $\tau$, żeby było przekształceniem skalarnym:
1. Symetryczność $\tau(x, y) = \tau(y, x)$
2. Addytywność $\tau(x + z, y) = \tau(x, y) + \tau(z, y)$
3. Jednorodność $\tau(\alpha x, y) = \alpha * \tau(x, y)$
4. Dodatnia określoność $\tau(x, x) > 0$ dla $x \neq 0$ oraz $\tau(x, x) = 0 \iff x = 0$

## Baza ortogonalna

To taka baza, gdzie wektory są do siebie prostopadłe, czyli ich iloczyn skalarny wynosi 0.

## Ortogonalizacja Grama-Schmidta

Jest to iteracyjna metoda zamiany bazy na bazę ortogonalną.

Bierzemy po kolei wektory z bazy i dodajemy je do bazy ortoganlnej, w następujący sposób. Dla wektora $\vec{v}_i$ dodawanego do bazy jego wersja która można dodać do bazy ortogonalnej to $\vec{v}_i' = \vec{v}_i - \sum_{j=1}^{i-1} (\frac{\tau(\vec{v}_i, \vec{v}_j')}{\tau(\vec{v}_j', \vec{v}_j')} \vec{v}_j')$.

Intuicja tego jest taka, że bierzemy wektor z bazy początkowej i dodajemy go do bazy ortogonalnej "zaprzyjaźniając" go z resztą wektorów, które już dodaliśmy do bazy.

"Zaprzyjaźnienie" to odjęcie rzutowania $\vec{v}_i$ na przestrzeń rozpinaną przez wektory, które już są w bazie ortogonalnej. 

## Normalizacja

Norma wektora to jego długość względem jakiegoś iloczynu skalarnego $\tau$ to $||\vec{v}|| = \sqrt{\tau(\vec{v}, \vec{v})}$

Możemy znormalizować wektor dzieląc go przez jego normę. Wtedy jego długość, względem danego iloczynu skalarnego będzie wynosiła $1$.

Jeżeli wszystkie wektory z bazy ortogonalnej znormalizujemy, to otrzymamy bazę ortonormalną.
