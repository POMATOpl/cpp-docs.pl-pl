---
description: 'Dowiedz się więcej na temat: Move Function'
title: Move — Funkcja
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
ms.openlocfilehash: eada3cac16abc445a9c48d01240f4ccf46d78372
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209311"
---
# <a name="move-function"></a>Move — Funkcja

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template<class T>
inline typename RemoveReference<T>::Type&& Move(
   _Inout_ T&& arg
);
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ argumentu.

*ARG*<br/>
Argument do przeniesienia.

## <a name="return-value"></a>Wartość zwracana

*Argument* Parameter po elemencie Reference lub rvalue-Reference (jeśli any) został usunięty.

## <a name="remarks"></a>Uwagi

Przenosi określony argument z jednej lokalizacji do innej.

Aby uzyskać więcej informacji, zobacz sekcję **przenoszenie semantyki** [rvalue Reference deklarator:  &&](../../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:** Internal. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL::D etails — przestrzeń nazw](microsoft-wrl-details-namespace.md)
