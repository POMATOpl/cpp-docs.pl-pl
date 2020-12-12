---
description: 'Dowiedz się więcej na temat: funkcja AsWeak —'
title: AsWeak — Funkcja
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: a02776f06aab4d7505b38fbb1120c36a82e97368
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175849"
---
# <a name="asweak-function"></a>AsWeak — Funkcja

Pobiera słabe odwołanie do określonego wystąpienia.

## <a name="syntax"></a>Składnia

```cpp
template<typename T>
HRESULT AsWeak(
   _In_ T* p,
   _Out_ WeakRef* pWeak
);
```

### <a name="parameters"></a>Parametry

*T*<br/>
Wskaźnik do typu parametru *p*.

*St*<br/>
Wystąpienie typu.

*pWeak*<br/>
Po zakończeniu tej operacji wskaźnik do słabego odwołania do parametru *p*.

## <a name="return-value"></a>Wartość zwracana

S_OK, jeśli ta operacja zakończyła się pomyślnie; w przeciwnym razie błąd HRESULT, który wskazuje przyczynę niepowodzenia.

## <a name="requirements"></a>Wymagania

**Nagłówek:** Client. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL, przestrzeń nazw](microsoft-wrl-namespace.md)
