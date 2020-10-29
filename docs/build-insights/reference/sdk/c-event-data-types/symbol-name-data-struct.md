---
title: Struktura SYMBOL_NAME_DATA
description: Informacje o strukturze SYMBOL_NAME_DATA zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SYMBOL_NAME_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 08c09f304f8cc90bd48a2cecc6771d90c997a7f4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920934"
---
# <a name="symbol_name_data-structure"></a>Struktura SYMBOL_NAME_DATA

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`SYMBOL_NAME_DATA`Struktura opisuje symbol frontonu kompilatora.

## <a name="syntax"></a>Składnia

```cpp
typedef struct SYMBOL_NAME_DATA_TAG
{
    unsigned long long  Key;
    const char*         Name;

} SYMBOL_NAME_DATA;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `Key` | Klucz symbolu. Ta wartość jest unikatowa w obrębie analizowanego śledzenia. |
| `Name` | Nazwa symbolu. |

## <a name="remarks"></a>Uwagi

Symbole pochodzące z dwóch różnych przebiegów frontonu kompilatora mogą mieć taką samą nazwę, ale inny klucz. W takim przypadku należy użyć nazw symboli, aby określić, czy dwa typy są takie same.

::: moniker-end
