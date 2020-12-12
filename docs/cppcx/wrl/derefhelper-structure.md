---
description: Dowiedz się więcej o strukturze DerefHelper —
title: DerefHelper — Struktura
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 8605e3923d8d3099a080be22f9d8e70ee9187ef9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272919"
---
# <a name="derefhelper-structure"></a>DerefHelper — Struktura

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template <typename T>
struct DerefHelper;

template <typename T>
struct DerefHelper<T*>;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Parametr szablonu.

## <a name="remarks"></a>Uwagi

Reprezentuje wskaźnik odwołujący się do `T*` parametru szablonu.

**DerefHelper —** jest używany w wyrażeniu, takim jak: `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`DerefType`|Identyfikator odwołania dla parametru szablonu `T*` .|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`DerefHelper`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Async. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL::D etails — przestrzeń nazw](microsoft-wrl-details-namespace.md)
