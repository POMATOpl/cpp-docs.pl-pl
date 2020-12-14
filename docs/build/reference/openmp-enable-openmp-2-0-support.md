---
description: Dowiedz się więcej o:/OpenMP (Włącz obsługę OpenMP)
title: /OpenMP (Włącz obsługę OpenMP)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: 818cd6167bf56b9948a3d9f455b0153b4302e8df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221985"
---
# <a name="openmp-enable-openmp-support"></a>/OpenMP (Włącz obsługę OpenMP)

Powoduje, że kompilator przetwarza [`#pragma omp`](../../preprocessor/omp.md) dyrektywy w obsłudze OpenMP.

## <a name="syntax"></a>Składnia

::: moniker range=">= msvc-160"

> **/OpenMP** \[ **:**__eksperymentalne__]

::: moniker-end

::: moniker range="<= msvc-150"

> **/OpenMP**

::: moniker-end

## <a name="remarks"></a>Uwagi

`#pragma omp` służy do określania [dyrektyw](../../parallel/openmp/reference/openmp-directives.md) i [klauzul](../../parallel/openmp/reference/openmp-clauses.md). Jeśli **/OpenMP** nie jest określony w kompilacji, kompilator ignoruje klauzule OpenMP i dyrektywy. Wywołania [funkcji OpenMP](../../parallel/openmp/reference/openmp-functions.md) są przetwarzane przez kompilator, nawet jeśli nie określono **/OpenMP** .

::: moniker range=">= msvc-160"

Kompilator języka C++ obsługuje obecnie standard OpenMP 2,0. Jednak program Visual Studio 2019 oferuje teraz również funkcje SIMD. Aby użyć SIMD, skompiluj przy użyciu opcji **/OpenMP: eksperymentalne** . Ta opcja włącza zarówno normalne funkcje OpenMP, jak i dodatkowe funkcje SIMD OpenMP niedostępne podczas korzystania z przełącznika **/OpenMP** .

::: moniker-end

Aplikacje skompilowane przy użyciu programu **/OpenMP** i **/CLR** można uruchamiać tylko w procesie domeny pojedynczego aplikacji. Wiele domen aplikacji nie jest obsługiwanych. Oznacza to, że po uruchomieniu konstruktora modułów ( `.cctor` ) wykrywa, czy proces jest kompilowany przy użyciu **/OpenMP**, a jeśli aplikacja jest załadowana do środowiska uruchomieniowego innego niż domyślne. Aby uzyskać więcej informacji, zobacz element [AppDomain](../../cpp/appdomain.md), [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](clr-common-language-runtime-compilation.md)i [inicjalizację zestawów mieszanych](../../dotnet/initialization-of-mixed-assemblies.md).

Jeśli podjęto próbę załadowania aplikacji skompilowanej przy użyciu programu **/OpenMP** i **/CLR** do domeny aplikacji innej niż domyślna, <xref:System.TypeInitializationException> wyjątek jest zgłaszany poza debugerem, a `OpenMPWithMultipleAppdomainsException` w debugerze zostanie zgłoszony wyjątek.

Te wyjątki mogą być również zgłaszane w następujących sytuacjach:

- Jeśli aplikacja jest kompilowana przy użyciu **/CLR** , ale nie **/OpenMP**, i jest załadowana do domeny aplikacji innej niż domyślna, gdzie proces obejmuje aplikację skompilowaną przy użyciu **/OpenMP**.

- Jeśli aplikacja **/CLR** zostanie przekazana do narzędzia, takiego jak [regasm.exe](/dotnet/framework/tools/regasm-exe-assembly-registration-tool), które ładuje jego zestawy docelowe do domeny aplikacji innej niż domyślna.

Zabezpieczenia dostępu kodu środowiska uruchomieniowego języka wspólnego nie działają w regionach OpenMP. Jeśli zastosujesz atrybut zabezpieczenia dostępu kodu CLR poza region równoległy, nie będzie on obowiązywać w regionie równoległym.

Firma Microsoft nie zaleca pisania aplikacji **/OpenMP** , które zezwalają na częściowo zaufane obiekty wywołujące. Nie używaj <xref:System.Security.AllowPartiallyTrustedCallersAttribute> ani żadnych atrybutów zabezpieczeń dostępu kodu CLR.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń   >  stronę właściwości konfiguracja języka **C/C++**  >   .

1. Zmodyfikuj właściwość **Obsługa OpenMP** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.

## <a name="example"></a>Przykład

Poniższy przykład pokazuje niektóre efekty uruchomienia puli wątków zamiast używania puli wątków po jej uruchomieniu. Przy założeniu, że procesor x64, pojedynczy rdzeń, dwuprocesorowy, Pula wątków trwa od 16 MS. Po tej dacie istnieje niewielki koszt dla puli wątków.

Gdy kompilujesz przy użyciu **/OpenMP**, drugie wywołanie TEST2 nigdy nie działa dłużej niż w przypadku kompilowania przy użyciu **/OpenMP-**, ponieważ nie ma uruchamiania puli wątków. W milionu iteracji wersja **/OpenMP** jest szybsza niż wersja **/OpenMP-** drugiego wywołania usługi TEST2. W przypadku 25 iteracji Rejestracja wersji **/OpenMP-** i **/OpenMP** jest mniejsza niż poziom szczegółowości zegara.

Jeśli w aplikacji jest tylko jedna pętla i działa ona w mniej niż 15 MS (dostosowane do przybliżonego obciążenia na maszynie), **/OpenMP** może być nieodpowiednia. Jeśli jest wyższa, warto rozważyć użycie **/OpenMP**.

```cpp
// cpp_compiler_options_openmp.cpp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>
#include <windows.h>

volatile DWORD dwStart;
volatile int global = 0;

double test2(int num_steps) {
   int i;
   global++;
   double x, pi, sum = 0.0, step;

   step = 1.0 / (double) num_steps;

   #pragma omp parallel for reduction(+:sum) private(x)
   for (i = 1; i <= num_steps; i++) {
      x = (i - 0.5) * step;
      sum = sum + 4.0 / (1.0 + x*x);
   }

   pi = step * sum;
   return pi;
}

int main(int argc, char* argv[]) {
   double   d;
   int n = 1000000;

   if (argc > 1)
      n = atoi(argv[1]);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);
}
```

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md) \
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md) \
[OpenMP w MSVC](../../parallel/openmp/openmp-in-visual-cpp.md)
