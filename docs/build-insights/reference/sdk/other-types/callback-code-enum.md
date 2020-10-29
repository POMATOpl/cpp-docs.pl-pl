---
title: CALLBACK_CODE Wyliczenie
description: Zestaw SDK usługi Build Insights w wersji C++ CALLBACK_CODE odwołanie.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CALLBACK_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 146d191d0b642ad538f5a314016b41fdbdf26113
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922592"
---
# <a name="callback_code-enum"></a>CALLBACK_CODE Wyliczenie

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`CALLBACK_CODE`Wyliczenie służy do sterowania przepływem analizy lub sesji ponownego rejestrowania. Zwróć CALLBACK_CODE wartość z funkcji w [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) lub [RELOG_CALLBACKS](relog-callbacks-struct.md) , aby kontrolować, co należy zrobić dalej.

## <a name="members"></a>Elementy członkowskie

| Nazwa | Wartość | Opis |
|--|--|--|
| `CALLBACK_CODE_ANALYSIS_SUCCESS` | 1 (0x00000001) | Kontynuuj bieżącą analizę lub rejestrowanie w normalnym sesji. |
| `CALLBACK_CODE_ANALYSIS_FAILURE` | 2 (0x00000002) | Anuluj bieżącą analizę lub przerejestrowanie sesji i sygnalizuj błąd. |
| `CALLBACK_CODE_ANALYSIS_CANCEL` | 4 (0x00000004) | Anuluj bieżącą analizę lub przerejestrowanie. |

::: moniker-end
