---
description: Dowiedz się więcej o strukturze tożsamości
title: identity — Struktura
ms.date: 11/04/2016
f1_keywords:
- utility/std::identity
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
ms.openlocfilehash: 753a3b697eb2a77dd102f681403fd23d7062cb36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231761"
---
# <a name="identity-structure"></a>identity — Struktura

Struktura, która dostarcza definicję typu jako parametr szablonu.

## <a name="syntax"></a>Składnia

```cpp
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
};
```

### <a name="parameters"></a>Parametry

*lewym*\
Wartość do zidentyfikowania.

## <a name="remarks"></a>Uwagi

Klasa zawiera definicję typu publicznego `type` , która jest taka sama jak typ parametru szablonu. Jest on używany w połączeniu z funkcją szablonu do [przodu](../standard-library/utility-functions.md#forward) , aby upewnić się, że parametr funkcji ma żądany typ.

Aby zapewnić zgodność ze starszym kodem, Klasa definiuje również funkcję Identity, `operator()` która zwraca jej argument *Left*.
