---
description: Dowiedz się więcej o strukturze CloakedIid —
title: CloakedIid — Struktura
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 06bddded27882ae1216064aafc311364a8d2fd9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338786"
---
# <a name="cloakediid-structure"></a>CloakedIid — Struktura

Wskazuje `RuntimeClass` , `Implements` i szablony, `ChainInterfaces` których określony interfejs nie jest dostępny na liście IID.

## <a name="syntax"></a>Składnia

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Interfejs, który jest ukryty (zamaskowany).

## <a name="remarks"></a>Uwagi

Poniżej przedstawiono przykład użycia **CloakedIid —** : `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}` .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`T`

`CloakedIid`

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL, przestrzeń nazw](microsoft-wrl-namespace.md)
