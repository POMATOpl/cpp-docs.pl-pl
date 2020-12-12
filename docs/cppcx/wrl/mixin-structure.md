---
description: Dowiedz się więcej o strukturze domieszki
title: MixIn — Struktura
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: a438fb6846ae6ba88aaaa968d7b94e8d6636c4aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209389"
---
# <a name="mixin-structure"></a>MixIn — Struktura

Zapewnia, że Klasa środowiska uruchomieniowego pochodzi z interfejsów środowisko wykonawcze systemu Windows, jeśli istnieje, a następnie do klasycznych interfejsów COM.

## <a name="syntax"></a>Składnia

```cpp
template<
    typename Derived,
    typename MixInType,
    bool hasImplements = __is_base_of(Details::ImplementsBase, MixInType)
>
struct MixIn;
```

### <a name="parameters"></a>Parametry

*Pochodne*<br/>
Typ pochodzący od struktury [implementującej](implements-structure.md) .

*MixInType*<br/>
Typ podstawowy.

*hasImplements*<br/>
**`true`** Jeśli *MixInType* jest pochodną bieżącej implementacji typu podstawowego; **`false`** w przeciwnym razie.

## <a name="remarks"></a>Uwagi

Jeśli klasa jest pochodną zarówno środowisko wykonawcze systemu Windows, jak i interfejsów COM, lista deklaracji klasy musi najpierw wyświetlić wszystkie interfejsy środowisko wykonawcze systemu Windows, a następnie wszystkie klasyczne interfejsy COM. **Domieszki** gwarantuje, że interfejsy są określone w poprawnej kolejności.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`MixIn`

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL, przestrzeń nazw](microsoft-wrl-namespace.md)
