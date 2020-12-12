---
description: 'Dowiedz się więcej na temat: autoprzetwarzanie równoległe i autowektoryzacji'
title: Automatyczna paralelizacja i wektoryzacja
ms.date: 11/04/2016
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
ms.openlocfilehash: 4de73924ab6c28335ea6fcf2e6473e74d68bd189
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338314"
---
# <a name="auto-parallelization-and-auto-vectorization"></a>Automatyczna paralelizacja i wektoryzacja

Automatyczne paralelizacji i automatyczne Wektoryzator zostały zaprojektowane w celu zapewnienia automatycznego wzrostu wydajności dla pętli w kodzie.

## <a name="auto-parallelizer"></a>Autoparalelizacji

Przełącznik kompilatora [/Qpar](../build/reference/qpar-auto-parallelizer.md) włącza *Automatyczne przetwarzanie równoległe* pętle w kodzie. Po określeniu tej flagi bez zmiany istniejącego kodu kompilator szacuje kod, aby znaleźć pętle, które mogą korzystać z przetwarzanie równoległe. Ponieważ może on znajdować pętle, które nie wykonują dużo miejsca, a tym samym nie będzie korzystać z przetwarzanie równoległe, a ponieważ każdy niezbędny przetwarzanie równoległe może engender w przypadku duplikowania puli wątków, dodatkowej synchronizacji lub innej operacji przetwarzania, która spowodowałaby spadek wydajności zamiast ulepszania, kompilator jest ostrożny w wyborze pętli, które parallelizes. Rozważmy na przykład poniższy przykład, w którym Górna granica pętli nie jest znana w czasie kompilacji:

```cpp
void loop_test(int u) {
   for (int i=0; i<u; ++i)
      A[i] = B[i] * C[i];
}
```

Ponieważ `u` może być niewielką wartością, kompilator nie będzie automatycznie zrównoleglanie tej pętli. Można jednak nadal chcieć ją przekazywać, ponieważ wiesz, że `u` zawsze będzie to duże. Aby włączyć funkcję autoprzetwarzanie równoległe, określ [pętlę #pragma (hint_parallel (n))](../preprocessor/loop.md), gdzie `n` to liczba wątków, które mają być zrównoleglanie w poprzek. W poniższym przykładzie kompilator podejmie próbę zrównoleglanie pętlę na 8 wątków.

```cpp
void loop_test(int u) {
#pragma loop(hint_parallel(8))
   for (int i=0; i<u; ++i)
      A[i] = B[i] * C[i];
}
```

Podobnie jak w przypadku wszystkich [dyrektyw pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md), `__pragma(loop(hint_parallel(n)))` obsługiwana jest również Alternatywna składnia pragma.

Istnieją pewne pętle, których kompilator nie może zrównoleglanie nawet wtedy, gdy chcesz. Oto przykład:

```cpp
#pragma loop(hint_parallel(8))
for (int i=0; i<upper_bound(); ++i)
    A[i] = B[i] * C[i];
```

Funkcja `upper_bound()` może ulec zmianie przy każdym wywołaniu. Ze względu na to, że górne ograniczenie nie może być znane, kompilator może emitować komunikat diagnostyczny wyjaśniający, dlaczego nie można zrównoleglanie tej pętli. W poniższym przykładzie pokazano pętlę, która może być równoległa, pętla, która nie może być równoległa, składnia kompilatora do użycia w wierszu polecenia oraz dane wyjściowe kompilatora dla każdej opcji wiersza polecenia:

```cpp
int A[1000];
void test() {
#pragma loop(hint_parallel(0))
    for (int i=0; i<1000; ++i) {
        A[i] = A[i] + 1;
    }

    for (int i=1000; i<2000; ++i) {
        A[i] = A[i] + 1;
    }
}
```

Kompilowanie za pomocą tego polecenia:

`cl d:\myproject\mylooptest.cpp /O2 /Qpar /Qpar-report:1`

daje następujące dane wyjściowe:

```Output
--- Analyzing function: void __cdecl test(void)
d:\myproject\mytest.cpp(4) : loop parallelized
```

Kompilowanie za pomocą tego polecenia:

`cl d:\myproject\mylooptest.cpp /O2 /Qpar /Qpar-report:2`

daje następujące dane wyjściowe:

```Output
--- Analyzing function: void __cdecl test(void)
d:\myproject\mytest.cpp(4) : loop parallelized
d:\myproject\mytest.cpp(4) : loop not parallelized due to reason '1008'
```

Zwróć uwagę na różnice w danych wyjściowych między opcjami dwóch różnych [/Qpar-report (poziom raportowania autoparalelizacji)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md) . `/Qpar-report:1` Wyświetla komunikaty paralelizacji tylko dla pętli, które zostały pomyślnie równoległe. `/Qpar-report:2` Wyświetla komunikaty paralelizacji zarówno dla zakończonych powodzeniem, jak i niepowodzeniem pętli parallelizations.

Aby uzyskać więcej informacji na temat kodów przyczyn i komunikatów, zobacz [wektoryzator i paralelizacji messages](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

## <a name="auto-vectorizer"></a>Autowektoryzator

Funkcja autowektoryzator analizuje pętle w kodzie i używa rejestrów wektorów i instrukcji na komputerze docelowym, jeśli jest to możliwe. Może to poprawić wydajność kodu. Kompilator kieruje instrukcje SSE2, AVX i AVX2 w procesorach Intel lub AMD lub instrukcje NEONu w procesorach ARM, zgodnie z przełącznikiem [/Arch](../build/reference/arch-minimum-cpu-architecture.md) .

Funkcja autowektoryzator może generować różne instrukcje niż określono przez `/arch` przełącznik. Te instrukcje są chronione przez sprawdzanie środowiska uruchomieniowego, aby upewnić się, że kod nadal działa poprawnie. Na przykład podczas kompilowania `/arch:SSE2` instrukcji SSE 4.2 mogą być emitowane. Sprawdzanie środowiska uruchomieniowego weryfikuje, czy funkcja SSE 4.2 jest dostępna na docelowym procesorze, i przechodzi do wersji w pętli, która nie jest instrukcją SSE 4.2, jeśli procesor nie obsługuje tych instrukcji.

Domyślnie funkcja autowektoryzator jest włączona. Jeśli chcesz porównać wydajność kodu w obszarze wektoryzacji, możesz użyć [pętli #pragma (no_vector)](../preprocessor/loop.md) , aby wyłączyć wektoryzacji danej pętli.

```cpp
#pragma loop(no_vector)
for (int i = 0; i < 1000; ++i)
   A[i] = B[i] + C[i];
```

Podobnie jak w przypadku wszystkich [dyrektyw pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md), `__pragma(loop(no_vector))` obsługiwana jest również Alternatywna składnia pragma.

Podobnie jak w przypadku opcji autoparalelizacji można określić opcję wiersza polecenia [/Qvec-Report (Auto-Wektoryzator Reporting Level)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md) , aby zgłosić pomyślnie tylko pętle wektorowe — `/Qvec-report:1` lub zarówno pomyślnie, jak i niepomyślnie zakończone pętle — `/Qvec-report:2` ).

Aby uzyskać więcej informacji na temat kodów przyczyn i komunikatów, zobacz [wektoryzator i paralelizacji messages](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

Aby zapoznać się z przykładem, jak działa wektoryzator, zobacz [Project Austin część 2 z 6: zwinięcie strony](https://devblogs.microsoft.com/cppblog/project-austin-part-2-of-6-page-curling/)

## <a name="see-also"></a>Zobacz też

[pętla](../preprocessor/loop.md)<br/>
[Programowanie równoległe w kodzie natywnym](/archive/blogs/nativeconcurrency)<br/>
[/Qpar (autoparalelizacji)](../build/reference/qpar-auto-parallelizer.md)<br/>
[/Qpar-report (poziom raportowania autoparalelizacji)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)<br/>
[/Qvec-Report (poziom raportowania autowektoryzator)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)<br/>
[Komunikaty wektoryzator i paralelizacji](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)
