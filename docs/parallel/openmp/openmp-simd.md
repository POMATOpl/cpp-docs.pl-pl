---
description: Dowiedz się więcej o rozszerzeniu SIMD
title: Rozszerzenie SIMD
ms.date: 03/20/2019
helpviewer_keywords:
- SIMD
- OpenMP in Visual C++, new features
- explicit parallelization, new features
ms.openlocfilehash: 58a3f29002c4e517a2019454dfe741dfb5352a3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342429"
---
# <a name="simd-extension"></a>Rozszerzenie SIMD

Visual C++ obsługuje obecnie standard OpenMP 2,0, jednak program Visual Studio 2019 oferuje również funkcje SIMD.

> [!NOTE]
> Aby użyć SIMD, skompiluj z `-openmp:experimental` przełącznikiem, który umożliwia dodatkowe funkcje OpenMP niedostępne podczas korzystania z `-openmp` przełącznika.
>
> `-openmp:experimental`Przełącznik subsumes `-openmp` , co oznacza, że wszystkie funkcje OpenMP 2,0 są uwzględniane w jego użyciu.

Aby uzyskać więcej informacji, zobacz [SIMD Extension to C++ OpenMP w programie Visual Studio](https://devblogs.microsoft.com/cppblog/simd-extension-to-c-openmp-in-visual-studio/).

## <a name="openmp-simd-in-visual-c"></a>SIMD OpenMP w Visual C++

OpenMP SIMD, wprowadzony w standardzie OpenMP 4,0, obiekty docelowe w celu wykonywania pętli przyjaznych dla wektorów. Za pomocą `simd` dyrektywy przed pętlą, kompilator może ignorować zależności wektorów, uczynić pętlę możliwą jako możliwą do wektora, a w związku z tym zamiarem, aby użytkownicy musieli mieć wiele iteracji pętli jednocześnie.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Visual C++ oferuje podobne dyrektywy pragma pętli non-OpenMP, podobnie jak `#pragma vector` i `#pragma ivdep` , ale z SIMD OpenMP, kompilator może wykonywać więcej czynności, takich jak:

- Zawsze można zignorować obecne zależności wektora.
- `/fp:fast` jest włączona w pętli.
- Pętle zewnętrzne i pętle z wywołaniami funkcji są przyjazne dla wektora.
- Zagnieżdżone pętle mogą być połączone w jedną pętlę i są przyjazne dla wektorów.
- Przyspieszenie hybrydowe z `#pragma omp for simd` programem, aby umożliwić duże i wielowartościowe wektory wielowątkowe i szczegółowe.  

W przypadku pętli przyjaznych dla wektorów kompilator pozostanie dyskretny, chyba że jest używany przełącznik dziennika obsługi wektora:

```cmd
    cl -O2 -openmp:experimental -Qvec-report:2 mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(96) : info C5001: Omp simd loop vectorized
```

W przypadku pętli nieprzyjaznych dla wektorów kompilator emituje każdy komunikat:

```cmd
    cl -O2 -openmp:experimental mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
```

### <a name="clauses"></a>Klauzule

Dyrektywa SIMD OpenMP może również przyjąć następujące klauzule w celu zwiększenia obsługi wektorów:

|Dyrektywę|Opis|
|---|---|
|`simdlen(length)`|Określ liczbę torów wektorowych.|
|`safelen(length)`|Określ odległość zależności wektora.|
|`linear(list[ : linear-step]`)|Liniowe mapowanie od zmiennej indukcji pętli na subskrypcję tablicy.|
|`aligned(list[ : alignment])`|Wyrównanie danych.|
|`private(list)`|Określ prywatyzacji danych.|
|`lastprivate(list)`|Określ prywatyzacji danych z ostateczną wartością z ostatniej iteracji.|
|`reduction(reduction-identifier:list)`|Określ dostosowane operacje zmniejszania.|
|`collapse(n)`|Pętla pętli łączenia.|

> [!NOTE]
> Nieefektywne klauzule SIMD są analizowane i ignorowane przez kompilator z ostrzeżeniem.
>
> Na przykład w poniższym kodzie przedstawiono Ostrzeżenie:
>
> ```c
>    #pragma omp simd simdlen(8)
>    for (i = 0; i < count; i++)
>    {
>        a[i] = a[i-1] + 1;
>        b[i] = *c + 1;
>        bar(i);
>    }
> ```
>
> ```Output
>    warning C4849: OpenMP 'simdlen' clause ignored in 'simd' directive
> ```

### <a name="example"></a>Przykład
  
Dyrektywa OpenMP SIMD zapewnia użytkownikom sposób na dyktowanie kompilatora, który jest przyjazny dla wektorów. Dodając adnotację do pętli z dyrektywą SIMD OpenMP, użytkownicy mogą wykonywać wiele iteracji pętli jednocześnie.

Na przykład następująca pętla jest oznaczona adnotacją z dyrektywą OpenMP SIMD. Nie istnieje idealny równoległość między iteracjami pętli, ponieważ istnieje zależność wstecz od [i] do [i-1], ale ze względu na dyrektywę SIMD, kompilator nadal może spakować kolejne iteracje pierwszej instrukcji w jednej instrukcji wektorowej i uruchamiać je równolegle.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

W związku z tym następująca przekształcona Forma wektorowa pętli jest **dozwolona** , ponieważ kompilator utrzymuje sekwencyjne zachowanie każdej iteracji pętli oryginalnej. Innymi słowy, jest `a[i]` wykonywane po `a[-1]` , `b[i]` jest po `a[i]` i wywołanie `bar` .

```c
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        b[i:i+3] = *c + 1;
        bar(i);
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

**Nie** można przenieść odwołania do pamięci z `*c` pętli, jeśli może ona być aliasem `a[i]` lub `b[i]` . Zmiana kolejności instrukcji wewnątrz jednej oryginalnej iteracji jest również niedozwolona, jeśli spowoduje ona przerwanie współzależności sekwencyjnej. Na przykład następująca przekształcona pętla nie jest dozwolona:

```c
    c = b;
    t = *c;
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        bar(i);            // illegal to reorder if bar[i] depends on b[i]
        b[i:i+3] = t + 1;  // illegal to move *c out of the loop
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

## <a name="see-also"></a>Zobacz też

[/OpenMP (Włącz obsługę OpenMP 2,0)](../../build/reference/openmp-enable-openmp-2-0-support.md)<br/>
