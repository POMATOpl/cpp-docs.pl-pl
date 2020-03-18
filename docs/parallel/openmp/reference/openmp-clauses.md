---
title: Klauzule OpenMP
ms.date: 03/20/2019
f1_keywords:
- OpenMP clauses
- copyin
- copyprivate
- default
- firstprivate
- if
- lastprivate
- nowait
- num_threads
- ordered
- private
- reduction
- schedule
- shared
helpviewer_keywords:
- OpenMP clauses
- copyin OpenMP clause
- copyprivate OpenMP clause
- default OpenMP clause
- defaults, OpenMP clause
- firstprivate OpenMP clause
- if OpenMP clause
- lastprivate OpenMP clause
- nowait OpenMP clause
- num_threads OpenMP clause
- ordered OpenMP clause
- private OpenMP clause
- reduction OpenMP clause
- schedule OpenMP clause
- shared OpenMP clause
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
ms.openlocfilehash: 92bd73fda5891b0bbf7393d1a7fda573d0f00263
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417048"
---
# <a name="openmp-clauses"></a>Klauzule OpenMP

Zawiera łącza do klauzul używanych w interfejsie API OpenMP.

Wizualizacja C++ obsługuje następujące klauzule OpenMP.

Ogólne atrybuty:

|Klauzula|Opis|
|------|-----------|
|[przypadku](#if-openmp)|Określa, czy pętla powinna być wykonywana równolegle, czy w szeregu.|
|[num_threads](#num-threads)|Ustawia liczbę wątków w zespole wątku.|
|[każe](#ordered-openmp-clauses)|Wymagane w przypadku instrukcji Parallel [for](openmp-directives.md#for-openmp) , jeśli [uporządkowana](openmp-directives.md#ordered-openmp-directives) dyrektywa ma być używana w pętli.|
|[schedule](#schedule)|Dotyczy dyrektywy [for](openmp-directives.md#for-openmp) .|
|[nowait](#nowait)|Zastępuje barierę niejawną w dyrektywie.|

W przypadku atrybutów udostępniania danych:

|Klauzula|Opis|
|------|-----------|
|[private](#private-openmp)|Określa, że każdy wątek powinien mieć własne wystąpienie zmiennej.|
|[firstprivate](#firstprivate)|Określa, że każdy wątek powinien mieć własne wystąpienie zmiennej i że zmienna powinna zostać zainicjowana przy użyciu wartości zmiennej, ponieważ istnieje przed równoległą konstrukcją.|
|[lastprivate](#lastprivate)|Określa, że wersja zmiennej otaczającego kontekstu jest równa prywatnej wersji danego wątku wykonuje ostateczną iterację (konstrukcja pętla) lub ostatnią sekcję (#pragma sekcje).|
|[udostępniać](#shared-openmp)|Określa, że co najmniej jedna zmienna powinna być współdzielona między wszystkie wątki.|
|[default](#default-openmp)|Określa zachowanie zmiennych nienależących do zakresu w równoległym regionie.|
|[reduction](#reduction)|Określa, że jedna lub więcej zmiennych, które są prywatne dla każdego wątku, jest podmiotem operacji zmniejszania na końcu regionu równoległego.|
|[copyin](#copyin)|Zezwala wątkom na dostęp do wartości wątku głównego dla zmiennej [threadprivate](openmp-directives.md#threadprivate) .|
|[copyprivate](#copyprivate)|Określa, że co najmniej jedna zmienna powinna być współdzielona między wszystkie wątki.|

## <a name="copyin"></a>copyin

Zezwala wątkom na dostęp do wartości wątku głównego dla zmiennej [threadprivate](openmp-directives.md#threadprivate) .

```cpp
copyin(var)
```

### <a name="parameters"></a>Parametry

*var*<br/>
Zmienna `threadprivate`, która zostanie zainicjowana przy użyciu wartości zmiennej w wątku głównym, która istnieje przed równoległą konstrukcją.

### <a name="remarks"></a>Uwagi

`copyin` ma zastosowanie do następujących dyrektyw:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [poszczególne](openmp-directives.md#sections-openmp)

Aby uzyskać więcej informacji, zobacz [2.7.2.7 Copy](../../../parallel/openmp/2-7-2-7-copyin.md).

### <a name="example"></a>Przykład

Zobacz [threadprivate](openmp-directives.md#threadprivate) , aby zapoznać się z przykładem korzystania z `copyin`.

## <a name="copyprivate"></a>copyprivate

Określa, że co najmniej jedna zmienna powinna być współdzielona między wszystkie wątki.

```cpp
copyprivate(var)
```

### <a name="parameters"></a>Parametry

*var*<br/>
Co najmniej jedna zmienna do udostępnienia. Jeśli określono więcej niż jedną zmienną, oddziel nazwy zmiennych przecinkami.

### <a name="remarks"></a>Uwagi

`copyprivate` dotyczy [pojedynczej](openmp-directives.md#single) dyrektywy.

Aby uzyskać więcej informacji, zobacz [2.7.2.8 copyprivate](../../../parallel/openmp/2-7-2-8-copyprivate.md).

### <a name="example"></a>Przykład

```cpp
// omp_copyprivate.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

float x, y, fGlobal = 1.0;
#pragma omp threadprivate(x, y)

float get_float() {
   fGlobal += 0.001;
   return fGlobal;
}

void use_float(float f, int t) {
   printf_s("Value = %f, thread = %d\n", f, t);
}

void CopyPrivate(float a, float b) {
   #pragma omp single copyprivate(a, b, x, y)
   {
      a = get_float();
      b = get_float();
      x = get_float();
      y = get_float();
    }

   use_float(a, omp_get_thread_num());
   use_float(b, omp_get_thread_num());
   use_float(x, omp_get_thread_num());
   use_float(y, omp_get_thread_num());
}

int main() {
   float a = 9.99, b = 123.456;

   printf_s("call CopyPrivate from a single thread\n");
   CopyPrivate(9.99, 123.456);

   printf_s("call CopyPrivate from a parallel region\n");
   #pragma omp parallel
   {
      CopyPrivate(a, b);
   }
}
```

```Output
call CopyPrivate from a single thread
Value = 1.001000, thread = 0
Value = 1.002000, thread = 0
Value = 1.003000, thread = 0
Value = 1.004000, thread = 0
call CopyPrivate from a parallel region
Value = 1.005000, thread = 0
Value = 1.005000, thread = 1
Value = 1.006000, thread = 0
Value = 1.006000, thread = 1
Value = 1.007000, thread = 0
Value = 1.007000, thread = 1
Value = 1.008000, thread = 0
Value = 1.008000, thread = 1
```

## <a name="default-openmp"></a>wartooć

Określa zachowanie zmiennych nienależących do zakresu w równoległym regionie.

```cpp
default(shared | none)
```

### <a name="remarks"></a>Uwagi

`shared`, która obowiązuje, Jeśli klauzula `default` nie została określona, oznacza, że jakakolwiek zmienna w regionie równoległym będzie traktowana jak jeśli została określona za pomocą klauzuli [Shared](#shared-openmp) . `none` oznacza, że wszystkie zmienne używane w równoległym regionie, które nie należą do zakresu w klauzuli [Private](#private-openmp), [Shared](#shared-openmp), [redukcyjne](#reduction), [firstprivate](#firstprivate)lub [lastprivate](#lastprivate) , spowodują błąd kompilatora.

`default` ma zastosowanie do następujących dyrektyw:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [poszczególne](openmp-directives.md#sections-openmp)

Aby uzyskać więcej informacji, zobacz [2.7.2.5 default](../../../parallel/openmp/2-7-2-5-default.md).

### <a name="example"></a>Przykład

Zapoznaj się z przykładem " [Private](#private-openmp) ", aby zapoznać się z `default`.

## <a name="firstprivate"></a>firstprivate

Określa, że każdy wątek powinien mieć własne wystąpienie zmiennej i że zmienna powinna zostać zainicjowana przy użyciu wartości zmiennej, ponieważ istnieje przed równoległą konstrukcją.

```cpp
firstprivate(var)
```

### <a name="parameters"></a>Parametry

*var*<br/>
Zmienna, która ma wystąpienia w każdym wątku i zostanie zainicjowana przy użyciu wartości zmiennej, ponieważ istnieje przed równoległą konstrukcją. Jeśli określono więcej niż jedną zmienną, oddziel nazwy zmiennych przecinkami.

### <a name="remarks"></a>Uwagi

`firstprivate` ma zastosowanie do następujących dyrektyw:

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [poszczególne](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Aby uzyskać więcej informacji, zobacz [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).

### <a name="example"></a>Przykład

Przykład użycia `firstprivate`można znaleźć w przykładowym [prywatnym](#private-openmp).

## <a name="if-openmp"></a>if (OpenMP)

Określa, czy pętla powinna być wykonywana równolegle, czy w szeregu.

```cpp
if(expression)
```

### <a name="parameters"></a>Parametry

*wyrażenia*<br/>
Całkowite wyrażenie, które zwraca wartość true (niezerowa), powoduje równoległe wykonywanie kodu w regionie równoległym. Jeśli wyrażenie zwróci wartość false (zero), region równoległy jest wykonywany w szeregu (za pomocą pojedynczego wątku).

### <a name="remarks"></a>Uwagi

`if` ma zastosowanie do następujących dyrektyw:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [poszczególne](openmp-directives.md#sections-openmp)

Aby uzyskać więcej informacji, zobacz [2,3 równoległa konstrukcja](../../../parallel/openmp/2-3-parallel-construct.md).

### <a name="example"></a>Przykład

```cpp
// omp_if.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void test(int val)
{
    #pragma omp parallel if (val)
    if (omp_in_parallel())
    {
        #pragma omp single
        printf_s("val = %d, parallelized with %d threads\n",
                 val, omp_get_num_threads());
    }
    else
    {
        printf_s("val = %d, serialized\n", val);
    }
}

int main( )
{
    omp_set_num_threads(2);
    test(0);
    test(2);
}
```

```Output
val = 0, serialized
val = 2, parallelized with 2 threads
```

## <a name="lastprivate"></a>lastprivate

Określa, że wersja zmiennej otaczającego kontekstu jest równa prywatnej wersji danego wątku wykonuje ostateczną iterację (konstrukcja pętla) lub ostatnią sekcję (#pragma sekcje).

```cpp
lastprivate(var)
```

### <a name="parameters"></a>Parametry

*var*<br/>
Zmienna, która jest ustawiona jako jest równa prywatnej wersji tego wątku, wykonuje ostateczną iterację (konstrukcja pętli) lub ostatnią sekcję (#pragma sekcje).

### <a name="remarks"></a>Uwagi

`lastprivate` ma zastosowanie do następujących dyrektyw:

- [for](openmp-directives.md#for-openmp)
- [poszczególne](openmp-directives.md#sections-openmp)

Aby uzyskać więcej informacji, zobacz [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).

### <a name="example"></a>Przykład

Zapoznaj się z przykładem [Zaplanuj](#schedule) , aby zapoznać się z klauzulą `lastprivate`.

## <a name="nowait"></a>nowait

Zastępuje barierę niejawną w dyrektywie.

```cpp
nowait
```

### <a name="remarks"></a>Uwagi

`nowait` ma zastosowanie do następujących dyrektyw:

- [for](openmp-directives.md#for-openmp)
- [poszczególne](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Aby uzyskać więcej informacji, zobacz [2.4.1 for konstrukcja](../../../parallel/openmp/2-4-1-for-construct.md), [2.4.2 sekcje konstrukcja](../../../parallel/openmp/2-4-2-sections-construct.md)i [2.4.3 Single konstrukcja](../../../parallel/openmp/2-4-3-single-construct.md).

### <a name="example"></a>Przykład

```cpp
// omp_nowait.cpp
// compile with: /openmp /c
#include <stdio.h>

#define SIZE 5

void test(int *a, int *b, int *c, int size)
{
    int i;
    #pragma omp parallel
    {
        #pragma omp for nowait
        for (i = 0; i < size; i++)
            b[i] = a[i] * a[i];

        #pragma omp for nowait
        for (i = 0; i < size; i++)
            c[i] = a[i]/2;
    }
}

int main( )
{
    int a[SIZE], b[SIZE], c[SIZE];
    int i;

    for (i=0; i<SIZE; i++)
        a[i] = i;

    test(a,b,c, SIZE);

    for (i=0; i<SIZE; i++)
        printf_s("%d, %d, %d\n", a[i], b[i], c[i]);
}
```

```Output
0, 0, 0
1, 1, 0
2, 4, 1
3, 9, 1
4, 16, 2
```

## <a name="num-threads"></a>num_threads

Ustawia liczbę wątków w zespole wątku.

```cpp
num_threads(num)
```

### <a name="parameters"></a>Parametry

*numerowan*<br/>
Liczba wątków

### <a name="remarks"></a>Uwagi

Klauzula `num_threads` ma takie same funkcje jak funkcja [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) .

`num_threads` ma zastosowanie do następujących dyrektyw:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [poszczególne](openmp-directives.md#sections-openmp)

Aby uzyskać więcej informacji, zobacz [2,3 równoległa konstrukcja](../../../parallel/openmp/2-3-parallel-construct.md).

### <a name="example"></a>Przykład

Zobacz [Parallel](openmp-directives.md#parallel) , aby poznać przykład użycia klauzuli `num_threads`.

## <a name="ordered-openmp-clauses"></a>każe

Wymagane w przypadku instrukcji Parallel [for](openmp-directives.md#for-openmp) , jeśli [uporządkowana](openmp-directives.md#ordered-openmp-directives) dyrektywa ma być używana w pętli.

```cpp
ordered
```

### <a name="remarks"></a>Uwagi

`ordered` dotyczy dyrektywy [for](openmp-directives.md#for-openmp) .

Aby uzyskać więcej informacji, zobacz [2.4.1 for konstrukcja](../../../parallel/openmp/2-4-1-for-construct.md).

### <a name="example"></a>Przykład

Zobacz " [uporządkowane](openmp-directives.md#ordered-openmp-directives) ", aby zapoznać się z przykładem klauzuli using `ordered`.

## <a name="private-openmp"></a>użytek

Określa, że każdy wątek powinien mieć własne wystąpienie zmiennej.

```cpp
private(var)
```

### <a name="parameters"></a>Parametry

*var*<br/>
Zmienna, która ma wystąpienia w każdym wątku.

### <a name="remarks"></a>Uwagi

`private` ma zastosowanie do następujących dyrektyw:

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [poszczególne](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Aby uzyskać więcej informacji, zobacz [2.7.2.1 Private](../../../parallel/openmp/2-7-2-1-private.md).

### <a name="example"></a>Przykład

```c
// openmp_private.c
// compile with: /openmp
#include <windows.h>
#include <assert.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SLEEP_THREAD 1
#define NUM_LOOPS 2

enum Types {
   ThreadPrivate,
   Private,
   FirstPrivate,
   LastPrivate,
   Shared,
   MAX_TYPES
};

int nSave[NUM_THREADS][MAX_TYPES][NUM_LOOPS] = {{0}};
int nThreadPrivate;

#pragma omp threadprivate(nThreadPrivate)
#pragma warning(disable:4700)

int main() {
   int nPrivate = NUM_THREADS;
   int nFirstPrivate = NUM_THREADS;
   int nLastPrivate = NUM_THREADS;
   int nShared = NUM_THREADS;
   int nRet = 0;
   int i;
   int j;
   int nLoop = 0;

   nThreadPrivate = NUM_THREADS;
   printf_s("These are the variables before entry "
           "into the parallel region.\n");
   printf_s("nThreadPrivate = %d\n", nThreadPrivate);
   printf_s("      nPrivate = %d\n", nPrivate);
   printf_s(" nFirstPrivate = %d\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d\n", nLastPrivate);
   printf_s("       nShared = %d\n\n", nShared);
   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel copyin(nThreadPrivate) private(nPrivate) shared(nShared) firstprivate(nFirstPrivate)
   {
      #pragma omp for schedule(static) lastprivate(nLastPrivate)
      for (i = 0 ; i < NUM_THREADS ; ++i) {
         for (j = 0 ; j < NUM_LOOPS ; ++j) {
            int nThread = omp_get_thread_num();
            assert(nThread < NUM_THREADS);

            if (nThread == SLEEP_THREAD)
               Sleep(100);
            nSave[nThread][ThreadPrivate][j] = nThreadPrivate;
            nSave[nThread][Private][j] = nPrivate;
            nSave[nThread][Shared][j] = nShared;
            nSave[nThread][FirstPrivate][j] = nFirstPrivate;
            nSave[nThread][LastPrivate][j] = nLastPrivate;
            nThreadPrivate = nThread;
            nPrivate = nThread;
            nShared = nThread;
            nLastPrivate = nThread;
            --nFirstPrivate;
         }
      }
   }

   for (i = 0 ; i < NUM_LOOPS ; ++i) {
      for (j = 0 ; j < NUM_THREADS ; ++j) {
         printf_s("These are the variables at entry of "
                  "loop %d of thread %d.\n", i + 1, j);
         printf_s("nThreadPrivate = %d\n",
                  nSave[j][ThreadPrivate][i]);
         printf_s("      nPrivate = %d\n",
                  nSave[j][Private][i]);
         printf_s(" nFirstPrivate = %d\n",
                  nSave[j][FirstPrivate][i]);
         printf_s("  nLastPrivate = %d\n",
                  nSave[j][LastPrivate][i]);
         printf_s("       nShared = %d\n\n",
                  nSave[j][Shared][i]);
      }
   }

   printf_s("These are the variables after exit from "
            "the parallel region.\n");
   printf_s("nThreadPrivate = %d (The last value in the "
            "master thread)\n", nThreadPrivate);
   printf_s("      nPrivate = %d (The value prior to "
            "entering parallel region)\n", nPrivate);
   printf_s(" nFirstPrivate = %d (The value prior to "
            "entering parallel region)\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d (The value from the "
            "last iteration of the loop)\n", nLastPrivate);
   printf_s("       nShared = %d (The value assigned, "
            "from the delayed thread, %d)\n\n",
            nShared, SLEEP_THREAD);
}
```

```Output
These are the variables before entry into the parallel region.
nThreadPrivate = 4
      nPrivate = 4
nFirstPrivate = 4
  nLastPrivate = 4
       nShared = 4

These are the variables at entry of loop 1 of thread 0.
nThreadPrivate = 4
      nPrivate = 1310720
nFirstPrivate = 4
  nLastPrivate = 1245104
       nShared = 3

These are the variables at entry of loop 1 of thread 1.
nThreadPrivate = 4
      nPrivate = 4488
nFirstPrivate = 4
  nLastPrivate = 19748
       nShared = 0

These are the variables at entry of loop 1 of thread 2.
nThreadPrivate = 4
      nPrivate = -132514848
nFirstPrivate = 4
  nLastPrivate = -513199792
       nShared = 4

These are the variables at entry of loop 1 of thread 3.
nThreadPrivate = 4
      nPrivate = 1206
nFirstPrivate = 4
  nLastPrivate = 1204
       nShared = 2

These are the variables at entry of loop 2 of thread 0.
nThreadPrivate = 0
      nPrivate = 0
nFirstPrivate = 3
  nLastPrivate = 0
       nShared = 0

These are the variables at entry of loop 2 of thread 1.
nThreadPrivate = 1
      nPrivate = 1
nFirstPrivate = 3
  nLastPrivate = 1
       nShared = 1

These are the variables at entry of loop 2 of thread 2.
nThreadPrivate = 2
      nPrivate = 2
nFirstPrivate = 3
  nLastPrivate = 2
       nShared = 2

These are the variables at entry of loop 2 of thread 3.
nThreadPrivate = 3
      nPrivate = 3
nFirstPrivate = 3
  nLastPrivate = 3
       nShared = 3

These are the variables after exit from the parallel region.
nThreadPrivate = 0 (The last value in the master thread)
      nPrivate = 4 (The value prior to entering parallel region)
nFirstPrivate = 4 (The value prior to entering parallel region)
  nLastPrivate = 3 (The value from the last iteration of the loop)
       nShared = 1 (The value assigned, from the delayed thread, 1)
```

## <a name="reduction"></a>szum

Określa, że jedna lub więcej zmiennych, które są prywatne dla każdego wątku, jest podmiotem operacji zmniejszania na końcu regionu równoległego.

```cpp
reduction(operation:var)
```

### <a name="parameters"></a>Parametry

*operacje*<br/>
Operator dla operacji, który ma zostać przekształcony na *zmienne na końcu* równoległego regionu.

*var*<br/>
Co najmniej jedna zmienna, dla której ma zostać obniżona skalarna. Jeśli określono więcej niż jedną zmienną, oddziel nazwy zmiennych przecinkami.

### <a name="remarks"></a>Uwagi

`reduction` ma zastosowanie do następujących dyrektyw:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [poszczególne](openmp-directives.md#sections-openmp)

Aby uzyskać więcej informacji, zobacz [2.7.2.6 — zmniejszenie](../../../parallel/openmp/2-7-2-6-reduction.md).

### <a name="example"></a>Przykład

```cpp
// omp_reduction.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SUM_START   1
#define SUM_END     10
#define FUNC_RETS   {1, 1, 1, 1, 1}

int bRets[5] = FUNC_RETS;
int nSumCalc = ((SUM_START + SUM_END) * (SUM_END - SUM_START + 1)) / 2;

int func1( ) {return bRets[0];}
int func2( ) {return bRets[1];}
int func3( ) {return bRets[2];}
int func4( ) {return bRets[3];}
int func5( ) {return bRets[4];}

int main( )
{
    int nRet = 0,
        nCount = 0,
        nSum = 0,
        i,
        bSucceed = 1;

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel reduction(+ : nCount)
    {
        nCount += 1;

        #pragma omp for reduction(+ : nSum)
        for (i = SUM_START ; i <= SUM_END ; ++i)
            nSum += i;

        #pragma omp sections reduction(&& : bSucceed)
        {
            #pragma omp section
            {
                bSucceed = bSucceed && func1( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func2( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func3( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func4( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func5( );
            }
        }
    }

    printf_s("The parallel section was executed %d times "
             "in parallel.\n", nCount);
    printf_s("The sum of the consecutive integers from "
             "%d to %d, is %d\n", 1, 10, nSum);

    if (bSucceed)
        printf_s("All of the functions, func1 through "
                 "func5 succeeded!\n");
    else
        printf_s("One or more of the functions, func1 "
                 "through func5 failed!\n");

    if (nCount != NUM_THREADS)
    {
        printf_s("ERROR: For %d threads, %d were counted!\n",
                 NUM_THREADS, nCount);
        nRet |= 0x1;
   }

    if (nSum != nSumCalc)
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                "but %d was reported!\n",
                SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x10;
    }

    if (bSucceed != (bRets[0] && bRets[1] &&
                     bRets[2] && bRets[3] && bRets[4]))
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                 "but %d was reported!\n",
                 SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x100;
    }
}
```

```Output
The parallel section was executed 4 times in parallel.
The sum of the consecutive integers from 1 to 10, is 55
All of the functions, func1 through func5 succeeded!
```

## <a name="schedule"></a>rozkład

Dotyczy dyrektywy [for](openmp-directives.md#for-openmp) .

```cpp
schedule(type[,size])
```

### <a name="parameters"></a>Parametry

*type*<br/>
Rodzaj planowania, `dynamic`, `guided`, `runtime`lub `static`.

*zmienia*<br/>
Obowiązkowe Określa rozmiar iteracji. *rozmiar* musi być liczbą całkowitą. Nieprawidłowy, gdy *Typ* jest `runtime`.

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [2.4.1 for konstrukcja](../../../parallel/openmp/2-4-1-for-construct.md).

### <a name="example"></a>Przykład

```cpp
// omp_schedule.cpp
// compile with: /openmp
#include <windows.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define STATIC_CHUNK 5
#define DYNAMIC_CHUNK 5
#define NUM_LOOPS 20
#define SLEEP_EVERY_N 3

int main( )
{
    int nStatic1[NUM_LOOPS],
        nStaticN[NUM_LOOPS];
    int nDynamic1[NUM_LOOPS],
        nDynamicN[NUM_LOOPS];
    int nGuided[NUM_LOOPS];

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel
    {
        #pragma omp for schedule(static, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStatic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(static, STATIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStaticN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, DYNAMIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamicN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(guided)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nGuided[i] = omp_get_thread_num( );
        }
    }

    printf_s("------------------------------------------------\n");
    printf_s("| static | static | dynamic | dynamic | guided |\n");
    printf_s("|    1   |    %d   |    1    |    %d    |        |\n",
             STATIC_CHUNK, DYNAMIC_CHUNK);
    printf_s("------------------------------------------------\n");

    for (int i=0; i<NUM_LOOPS; ++i)
    {
        printf_s("|    %d   |    %d   |    %d    |    %d    |"
                 "    %d   |\n",
                 nStatic1[i], nStaticN[i],
                 nDynamic1[i], nDynamicN[i], nGuided[i]);
    }

    printf_s("------------------------------------------------\n");
}
```

```Output
------------------------------------------------
| static | static | dynamic | dynamic | guided |
|    1   |    5   |    1    |    5    |        |
------------------------------------------------
|    0   |    0   |    0    |    2    |    1   |
|    1   |    0   |    3    |    2    |    1   |
|    2   |    0   |    3    |    2    |    1   |
|    3   |    0   |    3    |    2    |    1   |
|    0   |    0   |    2    |    2    |    1   |
|    1   |    1   |    2    |    3    |    3   |
|    2   |    1   |    2    |    3    |    3   |
|    3   |    1   |    0    |    3    |    3   |
|    0   |    1   |    0    |    3    |    3   |
|    1   |    1   |    0    |    3    |    2   |
|    2   |    2   |    1    |    0    |    2   |
|    3   |    2   |    1    |    0    |    2   |
|    0   |    2   |    1    |    0    |    3   |
|    1   |    2   |    2    |    0    |    3   |
|    2   |    2   |    2    |    0    |    0   |
|    3   |    3   |    2    |    1    |    0   |
|    0   |    3   |    3    |    1    |    1   |
|    1   |    3   |    3    |    1    |    1   |
|    2   |    3   |    3    |    1    |    1   |
|    3   |    3   |    0    |    1    |    3   |
------------------------------------------------
```

## <a name="shared-openmp"></a>udostępniać

Określa, że co najmniej jedna zmienna powinna być współdzielona między wszystkie wątki.

```cpp
shared(var)
```

### <a name="parameters"></a>Parametry

*var*<br/>
Co najmniej jedna zmienna do udostępnienia. Jeśli określono więcej niż jedną zmienną, oddziel nazwy zmiennych przecinkami.

### <a name="remarks"></a>Uwagi

Innym sposobem udostępniania zmiennych między wątkami jest klauzula [copyprivate](#copyprivate) .

`shared` ma zastosowanie do następujących dyrektyw:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [poszczególne](openmp-directives.md#sections-openmp)

Aby uzyskać więcej informacji, zobacz [2.7.2.4 Shared](../../../parallel/openmp/2-7-2-4-shared.md).

### <a name="example"></a>Przykład

Zapoznaj się z przykładem " [Private](#private-openmp) ", aby zapoznać się z `shared`.
