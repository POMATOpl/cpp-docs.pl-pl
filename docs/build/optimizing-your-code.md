---
description: Dowiedz się więcej o tym, jak zoptymalizować kod
title: Optymalizacja kodu
ms.date: 05/06/2019
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: 893e3dce64400d47026e478b081283e3f1d82262
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179801"
---
# <a name="optimizing-your-code"></a>Optymalizacja kodu

Optymalizacja pliku wykonywalnego pozwala uzyskać równowagę między szybkością szybkiego wykonywania a niewielkim rozmiarem kodu. W tym temacie omówiono niektóre mechanizmy zapewniane przez program Visual Studio w celu ułatwienia optymalizacji kodu.

## <a name="language-features"></a>Funkcje językowe

W poniższych tematach opisano niektóre funkcje optymalizacji w języku C/C++.

[Dyrektywy pragma i słowa kluczowe optymalizacji](optimization-pragmas-and-keywords.md) \
Lista słów kluczowych i pragm, których można użyć w kodzie w celu zwiększenia wydajności.

[Opcje kompilatora na liście według kategorii](reference/compiler-options-listed-by-category.md) \
Lista **/o** opcji kompilatora, które mają wpływ na szybkość wykonywania lub rozmiar kodu.

[Rvalue Reference deklarator:  &&](../cpp/rvalue-reference-declarator-amp-amp.md) \
Odwołania rvalue obsługują implementację *semantyki przenoszenia*. Jeśli semantyka przenoszenia jest używana do implementowania bibliotek szablonów, wydajność aplikacji korzystających z tych szablonów może znacząco poprawić.

### <a name="the-optimize-pragma"></a>Optymalizacja dyrektywy pragma

Jeśli zoptymalizowana sekcja kodu powoduje błędy lub spowolnienie, można użyć [optymalizacji](../preprocessor/optimize.md) pragma, aby wyłączyć optymalizację dla tej sekcji.

Ujmij kod między dwie dyrektywy pragma, jak pokazano poniżej:

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>Praktyki programowania

Podczas kompilowania kodu przy użyciu optymalizacji mogą być widoczne dodatkowe komunikaty ostrzegawcze. To zachowanie jest oczekiwane, ponieważ niektóre ostrzeżenia dotyczą tylko zoptymalizowanego kodu. Jeśli Zwróć te ostrzeżenia, można uniknąć wielu problemów z optymalizacją.

Paradoxically, Optymalizacja programu w celu przyspieszenia może spowodować wolniejsze działanie kodu. Wynika to z faktu, że pewne optymalizacje w celu zwiększenia rozmiaru kodu. Na przykład funkcje dekreślania eliminujeją obciążenie wywołań funkcji. Niepodkreślanie zbyt dużej ilości kodu może spowodować, że program jest tak duży, że liczba błędów stronicowania pamięci wirtualnej rośnie. W związku z tym szybkość działania wywołań funkcji eliminowania może zostać utracona w przypadku zamiany pamięci.

W poniższych tematach omówiono dobre praktyki programistyczne.

[Wskazówki dotyczące ulepszania kodu Time-Critical](tips-for-improving-time-critical-code.md) \
Lepsze techniki kodowania mogą przynieść lepszą wydajność. W tym temacie przedstawiono techniki kodowania, które mogą pomóc w upewnieniu się, że krytyczne elementy kodu działają prawidłowo.

[Najlepsze rozwiązania dotyczące optymalizacji](optimization-best-practices.md) \
Zawiera ogólne wytyczne dotyczące optymalnej optymalizacji aplikacji.

## <a name="debugging-optimized-code"></a>Debugowanie zoptymalizowanego kodu

Ponieważ Optymalizacja może zmienić kod utworzony przez kompilator, zalecamy debugowanie aplikacji i mierzenie jej wydajności, a następnie optymalizację kodu.

W poniższych tematach znajdują się informacje o sposobie debugowania kompilacji wydania.

- [Debugowanie w Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)

- [Porady: debugowanie zoptymalizowanego kodu](/visualstudio/debugger/how-to-debug-optimized-code)

- [Dlaczego liczby Floating-Point mogą utracić dokładnooć](why-floating-point-numbers-may-lose-precision.md)

W poniższych tematach przedstawiono informacje na temat optymalizowania kompilowania, ładowania i wykonywania kodu.

- [Optymalizowanie przepływności kompilatora](improving-compiler-throughput.md)

- [Korzystanie z nazwy funkcji bez () nie tworzy kodu](using-function-name-without-parens-produces-no-code.md)

- [Optymalizacja wbudowanego zestawu](../assembler/inline/optimizing-inline-assembly.md)

- [Określanie optymalizacji kompilatora dla projektu ATL](../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [Jakich technik optymalizacji należy użyć, aby zwiększyć wydajność aplikacji klienckiej podczas ładowania?](../build/dll-frequently-asked-questions.md#mfc_optimization)

## <a name="in-this-section"></a>W tej sekcji

[Dyrektywy pragma i słowa kluczowe optymalizacji](optimization-pragmas-and-keywords.md) \
[Optymalizowanie przepływności kompilatora](improving-compiler-throughput.md) \
[Dlaczego liczby Floating-Point mogą utracić dokładnooć](why-floating-point-numbers-may-lose-precision.md) \
[Reprezentacja IEEE Floating-Point](ieee-floating-point-representation.md) \
[Wskazówki dotyczące ulepszania kodu Time-Critical](tips-for-improving-time-critical-code.md) \
[Korzystanie z nazwy funkcji bez () nie tworzy kodu](using-function-name-without-parens-produces-no-code.md) \
[Najlepsze rozwiązania dotyczące optymalizacji](optimization-best-practices.md) \
[Optymalizacje profilowane](profile-guided-optimizations.md) \
[Zmienne środowiskowe dla optymalizacji Profile-Guided](environment-variables-for-profile-guided-optimizations.md) \
[PgoAutoSweep](pgoautosweep.md) \
[pgomgr](pgomgr.md) \
[pgosweep](pgosweep.md) \
[Instrukcje: scalanie wielu profili PGO w jeden profil](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)

## <a name="see-also"></a>Zobacz też

[Odwołanie kompilacji C/C++](reference/c-cpp-building-reference.md)
