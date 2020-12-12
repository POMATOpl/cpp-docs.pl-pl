---
description: 'Dowiedz się więcej o &lt; operatorze operatora (Microsoft:: WRL)'
title: 'operator operatora &lt; (Microsoft:: WRL)'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: 1edbb8218ef07355040bd05ab99db8f97be1cb59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330780"
---
# <a name="operatorlt-operator-microsoftwrl"></a>operator operatora &lt; (Microsoft:: WRL)

Określa, czy adres jednego obiektu jest mniejszy niż inny.

## <a name="syntax"></a>Składnia

```cpp
template<class T, class U>
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();
template<class T, class U>
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();
```

### <a name="parameters"></a>Parametry

*z*<br/>
Lewy obiekt.

*b*<br/>
Prawidłowy obiekt.

## <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli *adres jest mniejszy* niż adres *b*; w przeciwnym razie **`false`** .

## <a name="requirements"></a>Wymagania

**Nagłówek:** Client. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL, przestrzeń nazw](microsoft-wrl-namespace.md)
