---
description: 'Dowiedz się więcej na temat: A. Przykłady'
title: A. Przykłady
ms.date: 01/18/2019
ms.assetid: c0f6192f-a205-449b-b84c-cb30dbcc8b8f
ms.openlocfilehash: d52b59f9f83cf791c03fb49ca726273a2c977e58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342546"
---
# <a name="a-examples"></a>A. Przykłady

Poniżej przedstawiono przykłady konstrukcji zdefiniowanych w tym dokumencie. Instrukcja po dyrektywie jest złożona tylko wtedy, gdy jest to konieczne, a instrukcja niezłożona jest wcięty z dyrektywy poprzedzającej ją.

## <a name="a1-a-simple-loop-in-parallel"></a>A. 1 prosta pętla równoległa

W poniższym przykładzie pokazano, jak zrównoleglanie pętlę przy użyciu metody [Parallel for](2-directives.md#251-parallel-for-construct) . Zmienna iteracji pętli jest domyślnie prywatna, więc nie jest konieczna do określenia jej jawnie w klauzuli prywatnej.

```cpp
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```

## <a name="a2-conditional-compilation"></a>Kompilacja warunkowa A. 2

Poniższe przykłady ilustrują użycie kompilacji warunkowej przy użyciu makra OpenMP [_OPENMP](2-directives.md#22-conditional-compilation). W przypadku kompilacji OpenMP `_OPENMP` makro zostanie zdefiniowane.

```cpp
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

Zdefiniowany operator preprocesora umożliwia przetestowanie więcej niż jednego makra w jednej dyrektywie.

```cpp
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

## <a name="a3-parallel-regions"></a>A. 3 równoległe regiony

Dyrektywy [Parallel](2-directives.md#23-parallel-construct) można używać w programach równoległych ze grubym ziarnem. W poniższym przykładzie każdy wątek w regionie równoległym decyduje o tym, z której częścią tablicy globalnej `x` pracuje, na podstawie numeru wątku:

```cpp
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```

## <a name="a4-the-nowait-clause"></a>A. 4 klauzula nowait

Jeśli istnieje wiele niezależnych pętli w ramach równoległego regionu, można użyć klauzuli [nowait](2-directives.md#241-for-construct) , aby uniknąć implikowanej bariery na końcu `for` dyrektywy w następujący sposób:

```cpp
#pragma omp parallel
{
    #pragma omp for nowait
        for (i=1; i<n; i++)
             b[i] = (a[i] + a[i-1]) / 2.0;
    #pragma omp for nowait
        for (i=0; i<m; i++)
            y[i] = sqrt(z[i]);
}
```

## <a name="a5-the-critical-directive"></a>A. 5 Dyrektywa krytyczna

Poniższy przykład zawiera kilka dyrektyw o [znaczeniu krytycznym](2-directives.md#262-critical-construct) . Przykład ilustruje model kolejkowania, w którym zadanie jest podstawione i pracowało na nim. Aby zapewnić ochronę przed wieloma wątkami, należy w sekcji wykonać operację usuwania z kolejki `critical` . Ponieważ dwie kolejki w tym przykładzie są niezależne, są chronione przez `critical` dyrektywy o różnych nazwach, *liczbowa* i *YAxis*.

```cpp
#pragma omp parallel shared(x, y) private(x_next, y_next)
{
    #pragma omp critical ( xaxis )
        x_next = dequeue(x);
    work(x_next);
    #pragma omp critical ( yaxis )
        y_next = dequeue(y);
    work(y_next);
}
```

## <a name="a6-the-lastprivate-clause"></a>A. 6 klauzula lastprivate

Poprawne wykonanie jest czasami uzależnione od wartości, która Ostatnia iteracja pętli przypisuje do zmiennej. Takie programy muszą wyświetlać wszystkie takie zmienne jako argumenty dla klauzuli [lastprivate](2-directives.md#2723-lastprivate) , tak aby wartości zmiennych były takie same, jak gdy pętla jest wykonywana sekwencyjnie.

```cpp
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

W poprzednim przykładzie wartość `i` na końcu regionu równoległego będzie równa `n-1` , jak w przypadku sekwencyjnym.

## <a name="a7-the-reduction-clause"></a>A. 7 klauzula redukcji

Poniższy przykład ilustruje klauzulę [redukcji](2-directives.md#2726-reduction) :

```cpp
#pragma omp parallel for private(i) shared(x, y, n) \
                         reduction(+: a, b)
    for (i=0; i<n; i++) {
        a = a + x[i];
        b = b + y[i];
    }
```

## <a name="a8-parallel-sections"></a>A. 8 sekcje równoległe

W poniższym przykładzie (dla [sekcji 2.4.2](2-directives.md#242-sections-construct)) funkcje *liczbowa*, *YAxis* i *Zaxis* mogą być wykonywane współbieżnie. Pierwsza `section` dyrektywa jest opcjonalna.  Wszystkie `section` dyrektywy muszą pojawić się w zakresie leksykalnym `parallel sections` konstrukcji.

```cpp
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```

## <a name="a9-single-directives"></a>A. 9 pojedyncze dyrektywy

W poniższym przykładzie pokazano [pojedynczą](2-directives.md#243-single-construct) dyrektywę. W tym przykładzie tylko jeden wątek (zazwyczaj pierwszy wątek, który napotka `single` dyrektywę) drukuje komunikat o postępie. Użytkownik nie może wprowadzać żadnych założeń dotyczących tego, który wątek wykona `single` sekcję. Wszystkie pozostałe wątki pozostaną pominięte w `single` sekcji i przestaną się z bariery na końcu `single` konstrukcji. Jeśli inne wątki mogą działać bez oczekiwania na wątek wykonujący `single` sekcję, `nowait` można określić klauzulę w `single` dyrektywie.

```cpp
#pragma omp parallel
{
    #pragma omp single
        printf_s("Beginning work1.\n");
    work1();
    #pragma omp single
        printf_s("Finishing work1.\n");
    #pragma omp single nowait
        printf_s("Finished work1 and beginning work2.\n");
    work2();
}
```

## <a name="a10-sequential-ordering"></a>A. 10 porządkowanie sekwencyjne

[Uporządkowane sekcje](2-directives.md#266-ordered-construct) są przydatne do sekwencyjnego porządkowania danych wyjściowych z pracy, które są wykonywane równolegle. Następujący program drukuje indeksy w kolejności sekwencyjnej:

```cpp
#pragma omp for ordered schedule(dynamic)
    for (i=lb; i<ub; i+=st)
        work(i);
void work(int k)
{
    #pragma omp ordered
        printf_s(" %d", k);
}
```

## <a name="a11-a-fixed-number-of-threads"></a>A. 11 stała liczba wątków

Niektóre programy są zależne od ustalonej, określonej przez określoną liczbę wątków do poprawnego wykonania.  Ponieważ domyślnym ustawieniem dynamicznego dostosowywania liczby wątków jest zdefiniowana implementacja, takie programy mogą wyłączyć funkcję wątków dynamicznych i ustawić liczbę wątków jawnie, aby zachować przenośność. Poniższy przykład pokazuje, jak to zrobić przy użyciu [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function)i [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function):

```cpp
omp_set_dynamic(0);
omp_set_num_threads(16);
#pragma omp parallel shared(x, npoints) private(iam, ipoints)
{
    if (omp_get_num_threads() != 16)
      abort();
    iam = omp_get_thread_num();
    ipoints = npoints/16;
    do_by_16(x, iam, ipoints);
}
```

W tym przykładzie program jest wykonywany prawidłowo tylko wtedy, gdy jest wykonywany przez 16 wątków. Jeśli implementacja nie może obsługiwać 16 wątków, zachowanie tego przykładu jest zdefiniowane przez implementację.

Liczba wątków wykonujących region równoległy pozostaje stała w ramach równoległego regionu, niezależnie od ustawienia wątków dynamicznych. Mechanizm dynamiczne wątki określa liczbę wątków do użycia na początku równoległego regionu i utrzymuje stałą na czas trwania regionu.

## <a name="a12-the-atomic-directive"></a>A. 12 dyrektywa niepodzielna

Poniższy przykład pozwala uniknąć warunków wyścigu (równoczesnych aktualizacji elementu *x* przez wiele wątków) za pomocą dyrektywy [atomowej](2-directives.md#264-atomic-construct) :

```cpp
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

Zaletą korzystania z `atomic` dyrektywy w tym przykładzie jest to, że umożliwia równoległe przeprowadzanie aktualizacji dwóch różnych elementów x. Jeśli zamiast tego użyto dyrektywy [krytycznej](2-directives.md#262-critical-construct) , wszystkie aktualizacje elementów *x* są wykonywane szeregowo (choć nie w żadnej gwarantowanej kolejności).

`atomic`Dyrektywa ma zastosowanie tylko do instrukcji C lub C++ bezpośrednio po niej.  W związku z tym elementy *y* nie są aktualizowane w sposób niepodzielny w tym przykładzie.

## <a name="a13-a-flush-directive-with-a-list"></a>A. 13 dyrektywa Flush z listą

W poniższym przykładzie zastosowano `flush` dyrektywę dla synchronizacji typu punkt-punkt dla określonych obiektów między parami wątków:

```cpp
int   sync[NUMBER_OF_THREADS];
float work[NUMBER_OF_THREADS];
#pragma omp parallel private(iam,neighbor) shared(work,sync)
{
    iam = omp_get_thread_num();
    sync[iam] = 0;
    #pragma omp barrier

    // Do computation into my portion of work array
    work[iam] = ...;

    //  Announce that I am done with my work
    // The first flush ensures that my work is
    // made visible before sync.
    // The second flush ensures that sync is made visible.
    #pragma omp flush(work)
    sync[iam] = 1;
    #pragma omp flush(sync)

    // Wait for neighbor
    neighbor = (iam>0 ? iam : omp_get_num_threads()) - 1;
    while (sync[neighbor]==0)
    {
        #pragma omp flush(sync)
    }

    // Read neighbor's values of work array
    ... = work[neighbor];
}
```

## <a name="a14-a-flush-directive-without-a-list"></a>A. 14 dyrektywa Flush bez listy

Poniższy przykład (dla [sekcji 2.6.5](2-directives.md#265-flush-directive)) odróżnia obiekty udostępnione, których dotyczy `flush` dyrektywa, bez listy obiektów udostępnionych, których nie dotyczy:

```cpp
// omp_flush_without_list.c
#include <omp.h>

int x, *p = &x;

void f1(int *q)
{
    *q = 1;
    #pragma omp flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

void f2(int *q)
{
    #pragma omp barrier
    *q = 2;

    #pragma omp barrier
    // a barrier implies a flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

int g(int n)
{
    int i = 1, j, sum = 0;
    *p = 1;

    #pragma omp parallel reduction(+: sum) num_threads(10)
    {
        f1(&j);
        // i, n and sum were not flushed
        //   because they were not accessible in f1
        // j was flushed because it was accessible
        sum += j;
        f2(&j);
        // i, n, and sum were not flushed
        //   because they were not accessible in f2
        // j was flushed because it was accessible
        sum += i + j + *p + n;
    }
    return sum;
}

int main()
{
}
```

## <a name="a15-the-number-of-threads-used"></a>A. 15 Liczba używanych wątków

Rozważmy następujący nieprawidłowy przykład (dla [sekcji 3.1.2](3-run-time-library-functions.md#312-omp_get_num_threads-function)):

```cpp
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

`omp_get_num_threads()`Wywołanie zwraca 1 w sekcji szeregowej kodu, więc na przykład zawsze  będzie równa 1 w poprzednim przykładzie. Aby określić liczbę wątków, które zostaną wdrożone dla regionu równoległego, wywołanie powinno znajdować się wewnątrz regionu równoległego.

Poniższy przykład pokazuje, jak ponownie napisać ten program bez uwzględniania zapytania o liczbę wątków:

```cpp
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```

## <a name="a16-locks"></a>A. 16 blokad

W poniższym przykładzie (dla [sekcji 3,2](3-run-time-library-functions.md#32-lock-functions)) argument funkcji Lock powinien mieć typ `omp_lock_t` i nie ma potrzeby opróżniania.  Funkcje blokowania powodują, że wątki są bezczynne podczas oczekiwania na wpis w pierwszej sekcji krytycznej, ale w celu wykonania innych czynności podczas oczekiwania na wpis w drugim.  `omp_set_lock`Funkcja blokuje, ale `omp_test_lock` Funkcja nie zezwala na `skip()` wykonywane prace.

```cpp
// omp_using_locks.c
// compile with: /openmp /c
#include <stdio.h>
#include <omp.h>

void work(int);
void skip(int);

int main() {
   omp_lock_t lck;
   int id;

   omp_init_lock(&lck);
   #pragma omp parallel shared(lck) private(id)
   {
      id = omp_get_thread_num();

      omp_set_lock(&lck);
      printf_s("My thread id is %d.\n", id);

      // only one thread at a time can execute this printf
      omp_unset_lock(&lck);

      while (! omp_test_lock(&lck)) {
         skip(id);   // we do not yet have the lock,
                     // so we must do something else
      }
      work(id);     // we now have the lock
                    // and can do the work
      omp_unset_lock(&lck);
   }
   omp_destroy_lock(&lck);
}
```

## <a name="a17-nestable-locks"></a>A. 17 blokad zagnieżdżenia

Poniższy przykład (dla [sekcji 3,2](3-run-time-library-functions.md#32-lock-functions)) pokazuje, jak można użyć blokady możliwej do synchronizowania aktualizacji zarówno do całej struktury, jak i do jednego z jej elementów członkowskich.

```cpp
#include <omp.h>
typedef struct {int a,b; omp_nest_lock_t lck;} pair;

void incr_a(pair *p, int a)
{
    // Called only from incr_pair, no need to lock.
    p->a += a;
}

void incr_b(pair *p, int b)
{
    // Called both from incr_pair and elsewhere,
    // so need a nestable lock.

    omp_set_nest_lock(&p->lck);
    p->b += b;
    omp_unset_nest_lock(&p->lck);
}

void incr_pair(pair *p, int a, int b)
{
    omp_set_nest_lock(&p->lck);
    incr_a(p, a);
    incr_b(p, b);
    omp_unset_nest_lock(&p->lck);
}

void f(pair *p)
{
    extern int work1(), work2(), work3();
    #pragma omp parallel sections
    {
        #pragma omp section
            incr_pair(p, work1(), work2());
        #pragma omp section
            incr_b(p, work3());
    }
}
```

## <a name="a18-nested-for-directives"></a>A. 18 zagnieżdżenia dla dyrektyw

Poniższy przykład `for` [zagnieżdżania dyrektywy](2-directives.md#29-directive-nesting) jest zgodny ze względu na to, że dyrektywy wewnętrzne i zewnętrzne są `for` powiązane z różnymi regionami równoległymi:

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
        {
            #pragma omp parallel shared(i, n)
            {
                #pragma omp for
                    for (j=0; j<n; j++)
                        work(i, j);
            }
        }
}
```

Następująca odmiana powyższego przykładu jest również zgodna:

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
            work1(i, n);
}

void work1(int i, int n)
{
    int j;
    #pragma omp parallel default(shared)
    {
        #pragma omp for
            for (j=0; j<n; j++)
                work2(i, j);
    }
    return;
}
```

## <a name="a19-examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A. 19 przykłady pokazujące nieprawidłowe zagnieżdżanie dyrektyw udostępniania pracy

Przykłady w tej sekcji ilustrują reguły [zagnieżdżania dyrektywy](2-directives.md#29-directive-nesting) .

Poniższy przykład jest niezgodny, ponieważ dyrektywy wewnętrzne i zewnętrzne `for` są zagnieżdżone i powiązane z tą samą `parallel` dyrektywą:

```cpp
void wrong1(int n)
{
  #pragma omp parallel default(shared)
  {
      int i, j;
      #pragma omp for
      for (i=0; i<n; i++) {
          #pragma omp for
              for (j=0; j<n; j++)
                 work(i, j);
     }
   }
}
```

Następująca dynamicznie zagnieżdżona wersja powyższego przykładu jest również niezgodna:

```cpp
void wrong2(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++)
        work1(i, n);
  }
}

void work1(int i, int n)
{
  int j;
  #pragma omp for
    for (j=0; j<n; j++)
      work2(i, j);
}
```

Poniższy przykład jest niezgodny `for` , ponieważ dyrektywy i `single` są zagnieżdżone i są powiązane z tym samym regionem równoległym:

```cpp
void wrong3(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        #pragma omp single
          work(i);
      }
  }
}
```

Poniższy przykład jest niezgodny, ponieważ `barrier` dyrektywa wewnątrz `for` może spowodować zakleszczenie:

```cpp
void wrong4(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        work1(i);
        #pragma omp barrier
        work2(i);
      }
  }
}
```

Poniższy przykład jest niezgodny, ponieważ `barrier` powoduje zakleszczenie ze względu na fakt, że tylko jeden wątek w danym momencie może wprowadzić sekcję krytyczną:

```cpp
void wrong5()
{
  #pragma omp parallel
  {
    #pragma omp critical
    {
       work1();
       #pragma omp barrier
       work2();
    }
  }
}
```

Poniższy przykład jest niezgodny, ponieważ `barrier` powoduje zakleszczenie ze względu na fakt, że tylko jeden wątek wykonuje `single` sekcję:

```cpp
void wrong6()
{
  #pragma omp parallel
  {
    setup();
    #pragma omp single
    {
      work1();
      #pragma omp barrier
      work2();
    }
    finish();
  }
}
```

## <a name="a20-bind-barrier-directives"></a>A. 20 dyrektywy bariery powiązań

Reguły powiązań dyrektywy odwołują się do `barrier` dyrektywy, aby powiązać ją z najbliższą otaczającą `parallel` dyrektywą. Aby uzyskać więcej informacji na temat powiązania dyrektywy, zobacz [sekcję 2,8](2-directives.md#28-directive-binding).

W poniższym przykładzie wywołanie od *Main* do *sub2* jest zgodne, ponieważ `barrier` (in *sub3*) tworzy powiązanie z regionem równoległym w *sub2*. Wywołanie od *Main* do *sub1* jest zgodne, ponieważ `barrier` tworzy powiązanie z regionem równoległym w podprocedurie *sub2*.  Wywołanie od *Main* do *sub3* jest zgodne, ponieważ `barrier` nie jest powiązane z żadnym regionem równoległym i jest ignorowane. Ponadto `barrier` synchronizuje zespół wątków w otaczającym regionie równoległym, a nie wszystkie wątki utworzone w *sub1*.

```cpp
int main()
{
    sub1(2);
    sub2(2);
    sub3(2);
}

void sub1(int n)
{
    int i;
    #pragma omp parallel private(i) shared(n)
    {
        #pragma omp for
        for (i=0; i<n; i++)
            sub2(i);
    }
}

void sub2(int k)
{
     #pragma omp parallel shared(k)
     sub3(k);
}

void sub3(int n)
{
    work(n);
    #pragma omp barrier
    work(n);
}
```

## <a name="a21-scope-variables-with-the-private-clause"></a>A. 21 zmienne Scope z klauzulą prywatną

Wartości `i` i `j` w poniższym przykładzie są niezdefiniowane przy opuszczaniu z regionu równoległego:

```cpp
int i, j;
i = 1;
j = 2;
#pragma omp parallel private(i) firstprivate(j)
{
  i = 3;
  j = j + 2;
}
printf_s("%d %d\n", i, j);
```

Aby uzyskać więcej informacji na temat `private` klauzuli, zobacz [sekcję 2.7.2.1](2-directives.md#2721-private).

## <a name="a22-the-defaultnone-clause"></a>A. 22 klauzula default (None)

Poniższy przykład odróżnia zmienne, których dotyczy `default(none)` klauzula, ze zmiennych, które nie są:

```cpp
// openmp_using_clausedefault.c
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int x, y, z[1000];
#pragma omp threadprivate(x)

void fun(int a) {
   const int c = 1;
   int i = 0;

   #pragma omp parallel default(none) private(a) shared(z)
   {
      int j = omp_get_num_thread();
             //O.K.  - j is declared within parallel region
      a = z[j];       // O.K.  - a is listed in private clause
                      //      - z is listed in shared clause
      x = c;          // O.K.  - x is threadprivate
                      //      - c has const-qualified type
      z[i] = y;       // C3052 error - cannot reference i or y here

      #pragma omp for firstprivate(y)
         for (i=0; i<10 ; i++) {
            z[i] = y;  // O.K. - i is the loop control variable
                       // - y is listed in firstprivate clause
          }
       z[i] = y;   // Error - cannot reference i or y here
   }
}
```

Aby uzyskać więcej informacji na temat `default` klauzuli, zobacz [sekcję 2.7.2.5](2-directives.md#2725-default).

## <a name="a23-examples-of-the-ordered-directive"></a>A. 23 przykłady uporządkowanej dyrektywy

Możliwe jest posiadanie wielu uporządkowanych sekcji z `for` określoną `ordered` klauzulą. Pierwszy przykład jest niezgodny, ponieważ interfejs API określa następującą regułę:

"Iteracja pętli z `for` konstrukcyjną nie może wykonać tej samej `ordered` dyrektywy więcej niż raz i nie może wykonać więcej niż jednej `ordered` dyrektywy". (Zobacz [sekcję 2.6.6](2-directives.md#266-ordered-construct)).

W tym niezgodnym przykładzie wszystkie iteracje wykonują dwie uporządkowane sekcje:

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    #pragma omp ordered
    { ... }
    ...
    #pragma omp ordered
    { ... }
    ...
}
```

Poniższy zgodny przykład przedstawia `for` z więcej niż jedną sekcją uporządkowaną:

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    if (i <= 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
    (i > 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
}
```

## <a name="a24-example-of-the-private-clause"></a>A. 24 przykład klauzuli prywatnej

Klauzula [Private](2-directives.md#2721-private) regionu równoległego działa tylko dla leksykalnego zakresu regionu, a nie do dynamicznego zakresu regionu.  W związku z tym w powyższym przykładzie wszystkie zastosowania zmiennej *a* w `for` pętli w procedurze *f* odwołuje się do prywatnej kopii, a użycie w ramach procedury *g* odwołuje się do globalnej *a*.

```cpp
int a;

void f(int n)
{
    a = 0;

    #pragma omp parallel for private(a)
    for (int i=1; i<n; i++)
    {
        a = i;
        g(i, n);
        d(a);     // Private copy of "a"
        ...
    }
    ...

void g(int k, int n)
{
    h(k,a); // The global "a", not the private "a" in f
}
```

## <a name="a25-examples-of-the-copyprivate-data-attribute-clause"></a>A. 25 przykłady klauzuli copyprivate Data Attribute

**Przykład 1:** Klauzula [copyprivate](2-directives.md#2728-copyprivate) może służyć do emisji wartości uzyskanych przez pojedynczy wątek bezpośrednio do wszystkich wystąpień zmiennych prywatnych w innych wątkach.

```cpp
float x, y;
#pragma omp threadprivate(x, y)

void init( )
{
    float a;
    float b;

    #pragma omp single copyprivate(a,b,x,y)
    {
        get_values(a,b,x,y);
    }

    use_values(a, b, x, y);
}
```

W przypadku wywołania procedury *init* z regionu szeregowego jego zachowanie nie ma wpływ na obecność dyrektyw. Gdy wywołanie procedury *get_values* zostało wykonane przez jeden wątek, żaden wątek nie opuszcza konstrukcji do momentu, gdy obiekty prywatne wyznaczony przez *,* *b*, *x* i *y* we wszystkich wątkach nie zostaną zdefiniowane z wartościami odczytanymi.

**Przykład 2:** W przeciwieństwie do poprzedniego przykładu Załóżmy, że odczyt musi być wykonywany przez określony wątek, Wymów wątek główny. W tym przypadku `copyprivate` klauzula nie może być używana do bezpośredniej emisji, ale może służyć do zapewnienia dostępu do tymczasowego obiektu udostępnionego.

```cpp
float read_next( )
{
    float * tmp;
    float return_val;

    #pragma omp single copyprivate(tmp)
    {
        tmp = (float *) malloc(sizeof(float));
    }

    #pragma omp master
    {
        get_float( tmp );
    }

    #pragma omp barrier
    return_val = *tmp;
    #pragma omp barrier

    #pragma omp single
    {
       free(tmp);
    }

    return return_val;
}
```

**Przykład 3:** Załóżmy, że nie można łatwo określić liczby obiektów blokowania wymaganych w ramach równoległego regionu przed wprowadzeniem go. `copyprivate`Klauzula może służyć do zapewnienia dostępu do współużytkowanych obiektów blokady, które są przydzielone w tym regionie równoległym.

```cpp
#include <omp.h>

omp_lock_t *new_lock()
{
    omp_lock_t *lock_ptr;

    #pragma omp single copyprivate(lock_ptr)
    {
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));
        omp_init_lock( lock_ptr );
    }

    return lock_ptr;
}
```

## <a name="a26-the-threadprivate-directive"></a>A. 26 dyrektywa threadprivate

W poniższych przykładach pokazano, jak za pomocą dyrektywy [threadprivate](2-directives.md#271-threadprivate-directive) przydzielić każdy wątek osobnym licznikiem.

### <a name="example-1"></a>Przykład 1

```cpp
int counter = 0;
#pragma omp threadprivate(counter)

int sub()
{
    counter++;
    return(counter);
}
```

### <a name="example-2"></a>Przykład 2

```cpp
int sub()
{
    static int counter = 0;
    #pragma omp threadprivate(counter)
    counter++;
    return(counter);
}
```

## <a name="a27-c99-variable-length-arrays"></a>A. 27 tablic o zmiennej długości C99

Poniższy przykład ilustruje sposób używania tablic C99 o zmiennej długości (VLAs) w dyrektywie [firstprivate](2-directives.md#2722-firstprivate) .

> [!NOTE]
> Tablice o zmiennej długości nie są obecnie obsługiwane w Visual C++.

```cpp
void f(int m, int C[m][m])
{
    double v1[m];
    ...
    #pragma omp parallel firstprivate(C, v1)
    ...
}
```

## <a name="a28-the-num_threads-clause"></a>A. 28 klauzula num_threads

Poniższy przykład demonstruje klauzulę [num_threads](2-directives.md#23-parallel-construct) . Region równoległy jest wykonywany z maksymalnie 10 wątkami.

```cpp
#include <omp.h>
main()
{
    omp_set_dynamic(1);
    ...
    #pragma omp parallel num_threads(10)
    {
        ... parallel region ...
    }
}
```

## <a name="a29-work-sharing-constructs-inside-a-critical-construct"></a>A. 29 konstrukcje udostępniania pracy wewnątrz konstrukcji krytycznej

Poniższy przykład ilustruje użycie konstrukcji podziału pracy w `critical` konstrukcji. Ten przykład jest zgodny, ponieważ konstrukcja i konstrukcja udostępniania pracy `critical` nie są powiązane z tym samym regionem równoległym.

```cpp
void f()
{
  int i = 1;
  #pragma omp parallel sections
  {
    #pragma omp section
    {
      #pragma omp critical (name)
      {
        #pragma omp parallel
        {
          #pragma omp single
          {
            i++;
          }
        }
      }
    }
  }
}
```

## <a name="a30-reprivatization"></a>A. 30 reprywatyzacji

Poniższy przykład demonstruje reprywatyzacji zmiennych. Zmienne prywatne można oznaczyć `private` ponownie w dyrektywie zagnieżdżonej. Nie musisz udostępniać tych zmiennych w otaczającym regionie równoległym.

```cpp
int i, a;
...
#pragma omp parallel private(a)
{
  ...
  #pragma omp parallel for private(a)
  for (i=0; i<10; i++)
     {
       ...
     }
}
```

## <a name="a31-thread-safe-lock-functions"></a>A. 31 funkcje bezpiecznego blokowania wątków

Poniższy przykład języka C++ pokazuje, jak zainicjować tablicę blokad w regionie równoległym przy użyciu [omp_init_lock](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions).

```cpp
// A_13_omp_init_lock.cpp
// compile with: /openmp
#include <omp.h>

omp_lock_t *new_locks() {
   int i;
   omp_lock_t *lock = new omp_lock_t[1000];
   #pragma omp parallel for private(i)
   for (i = 0 ; i < 1000 ; i++)
      omp_init_lock(&lock[i]);

   return lock;
}

int main () {}
```
