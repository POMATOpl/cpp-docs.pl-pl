---
title: Struktura INVOCATION_DATA
description: Informacje o strukturze INVOCATION_DATA zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 98ac234b702ef2c73a5c8d90ee6bf4dc59349ed6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920973"
---
# <a name="invocation_data-structure"></a>Struktura INVOCATION_DATA

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`INVOCATION_DATA`Struktura opisuje wywołanie kompilatora lub konsolidatora.

## <a name="syntax"></a>Składnia

```cpp
typedef struct INVOCATION_DATA_TAG
{
    int                         MSVCToolCode;

    INVOCATION_VERSION_DATA     ToolVersion;

    const char*                 ToolVersionString;
    const wchar_t*              WorkingDirectory;
    const wchar_t*              ToolPath;

} INVOCATION_DATA;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `MSVCToolCode` | Kod, który identyfikuje typ wywołania. Aby uzyskać więcej informacji, zobacz [MSVC_TOOL_CODE](msvc-tool-code-enum.md). |
| `ToolVersion` | Obiekt, w którym jest przechowywana wywołana wersja narzędzia jako Grupa wartości całkowitych. |
| `ToolVersionString` | Opisuje wersję wywoływanego narzędzia w postaci tekstowej. |
| `WorkingDirectory` | Katalog, z którego wykonano wywołanie. |
| `ToolPath` | Ścieżka bezwzględna narzędzia wywoływanego. |

::: moniker-end
