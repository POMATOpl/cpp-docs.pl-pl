---
description: Dowiedz się więcej o:/Q opcje (operacje na niskim poziomie)
title: /Q Opcje (Operacje na niskim poziomie)
ms.date: 01/08/2020
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: f01781dd670c128f65717a05c6a9367e126550e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225716"
---
# <a name="q-options-low-level-operations"></a>/Q Opcje (Operacje na niskim poziomie)

Można użyć **/q** opcji kompilatora, aby wykonać następujące operacje kompilatora niskiego poziomu:

- [/Qfast_transcendentals (Wymuś szybkie transcendentals)](qfast-transcendentals-force-fast-transcendentals.md): generuje szybkie transcendentals.

- [/QIfist (pomijaj _ftol)](qifist-suppress-ftol.md): pomija `_ftol` , gdy wymagana jest konwersja typu zmiennoprzecinkowego na typ Integer (tylko x86).

- [/Qimprecise_fwaits (Usuń fwaits wewnątrz bloków try)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): usuwa `fwait` polecenia wewnątrz **`try`** bloków.

- [/QIntel-JCC-Erratum](qintel-jcc-erratum.md): zmniejsza wpływ na wydajność spowodowany przez aktualizację sprawdzenia erraty włączenia MIKROKODU (JCC) firmy Intel.

- [/Qpar (automatyczne paralelizacji)](qpar-auto-parallelizer.md): włącza automatyczne przetwarzanie równoległe pętli, które są oznaczone za pomocą dyrektywy [#pragma loop ()](../../preprocessor/loop.md) .

- [/Qpar-report (poziom raportowania automatycznej paralelizacji)](qpar-report-auto-parallelizer-reporting-level.md): włącza poziomy raportowania dla automatycznej przetwarzanie równoległe.

- [/Qsafe_fp_loads](qsafe-fp-loads.md): Pomija optymalizacje dla ładunków zmiennoprzecinkowych i umożliwia przenoszenie między pamięcią a rejestrem MMX.

- [/Qspectre](qspectre.md): generuje instrukcje w celu ograniczenia niektórych luk w zabezpieczeniach Spectre.

- [/Qspectre-Load](qspectre-load.md): generuje instrukcje w celu ograniczenia Spectre luk w zabezpieczeniach opartych na ładowaniu.

- [/Qspectre-Load-CF](qspectre-load-cf.md): generuje instrukcje w celu ograniczenia Spectre luk w zabezpieczeniach na podstawie instrukcji przepływu sterowania, które ładują.

- [/Qvec-Report (poziom raportowania automatycznej wektoryzator)](qvec-report-auto-vectorizer-reporting-level.md): włącza poziomy raportowania dla automatycznej wektoryzacji.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
