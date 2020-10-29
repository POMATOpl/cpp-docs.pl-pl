---
title: Struktura ANALYSIS_DESCRIPTOR
description: Informacje o strukturze ANALYSIS_DESCRIPTOR zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ec2d0a76618d6ff2cf0e7fdff7e360a4fd2e0174
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919855"
---
# <a name="analysis_descriptor-structure"></a>Struktura ANALYSIS_DESCRIPTOR

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`ANALYSIS_DESCRIPTOR`Struktura jest używana z funkcjami [Analizuj](../functions/analyze-a.md) i [AnalyzeW](../functions/analyze-w.md) . Opisano w nim, jak należy analizować śledzenie zdarzeń systemu Windows (ETW).

## <a name="syntax"></a>Składnia

```cpp
typedef struct ANALYSIS_DESCRIPTOR_TAG
{
    unsigned                NumberOfPasses;
    ANALYSIS_CALLBACKS      Callbacks;
    void*                   Context;
} ANALYSIS_DESCRIPTOR;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `NumberOfPasses` | Liczba przebiegów analizy, które powinny być wykonywane przez śledzenie ETW. |
| `Callbacks` | Obiekt [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) , który określa funkcje, które mają być wywoływane podczas sesji analizy. |
| `Context` | Kontekst udostępniony przez użytkownika, który jest przekazywany jako argument do wszystkich funkcji wywołania zwrotnego określonych w `Callbacks` |

## <a name="remarks"></a>Uwagi

`Callbacks`Struktura akceptuje tylko wskaźniki do funkcji nienależących do elementu członkowskiego. Aby obejść to ograniczenie, można ustawić `Context` wskaźnik obiektu. Wskaźnik tego obiektu zostanie przekazaną jako argument do wszystkich funkcji wywołania zwrotnego, które nie są elementami członkowskimi. Ten wskaźnik służy do wywoływania funkcji Członkowskich z poziomu funkcji wywołania zwrotnego, które nie są elementami członkowskimi.

::: moniker-end
