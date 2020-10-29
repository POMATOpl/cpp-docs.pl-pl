---
title: Klasa wyliczeniowa AnalysisControl
description: Odwołanie do wyliczenia zestawu SDK usługi Build Insights AnalysisControl.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 0f4887d626c5e80a0afaa393e255f8ffedbd6b1f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922624"
---
# <a name="analysiscontrol-enum-class"></a>Klasa wyliczeniowa AnalysisControl

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`AnalysisControl`Klasa enum służy do sterowania przepływem analizy lub sesji ponownego rejestrowania. Zwróć `AnalysisControl` kod z funkcji składowej [IAnalyzer](ianalyzer-class.md) lub [IRelogger](irelogger-class.md) , aby kontrolować, co powinno się stać dalej.

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `BLOCK` | Zapobiega dalszemu propagowaniu bieżącego zdarzenia w analizatorze lub grupie rejestratora. |
| `CANCEL` | Anuluj bieżącą analizę lub przerejestrowanie. |
| `CONTINUE` | Kontynuuj bieżącą analizę lub rejestrowanie w normalnym sesji. Propaguj bieżące zdarzenie do następnego elementu członkowskiego analizatora lub grupy ponownego rejestrowania. |
| `FAILURE` | Anuluj bieżącą analizę lub przerejestrowanie sesji i sygnalizuj błąd. |

::: moniker-end
