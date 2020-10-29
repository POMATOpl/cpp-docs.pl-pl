---
title: Struktura CL_PASS_DATA
description: Informacje o strukturze CL_PASS_DATA zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 24e524b802a124f38043f3b69afed7f1aa9cd156
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923646"
---
# <a name="cl_pass_data-structure"></a>Struktura CL_PASS_DATA

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`CL_PASS_DATA`Struktura zawiera opis przebiegu kompilacji.

## <a name="syntax"></a>Składnia

```cpp
typedef struct CL_PASS_DATA_TAG
{
    int                         TranslationUnitPassCode;
    const wchar_t*              InputSourcePath;
    const wchar_t*              OutputObjectPath;

} CL_PASS_DATA;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `TranslationUnitPassCode` | Kod identyfikujący przebieg kompilacji. Aby uzyskać więcej informacji, zobacz [TRANSLATION_UNIT_PASS_CODE](translation-unit-pass-code-enum.md). |
| `InputSourcePath` | Plik źródłowy C lub C++, w którym jest wykonywane wykonywanie kompilacji. |
| `OutputObjectPath` | Plik obiektu tworzony przez kompilator. |

::: moniker-end
