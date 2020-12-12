---
description: 'Dowiedz się więcej na temat: funkcja ActivateInstance —'
title: ActivateInstance — Funkcja
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
ms.openlocfilehash: 03d7b67810ee2ab287072546b098f81f43687233
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287856"
---
# <a name="activateinstance-function"></a>ActivateInstance — Funkcja

Rejestruje i Pobiera wystąpienie określonego typu zdefiniowane w określonym IDENTYFIKATORze klasy.

## <a name="syntax"></a>Składnia

```cpp
template<typename T>
inline HRESULT ActivateInstance(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance
);
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ do uaktywnienia.

*Wpisy*<br/>
Nazwa identyfikatora klasy, który definiuje parametr *T*.

*np*<br/>
Po zakończeniu tej operacji odwołanie do wystąpienia *T*.

## <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie błąd HRESULT, który wskazuje przyczynę błędu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** Client. h

**Przestrzeń nazw:** Windows:: Foundation

## <a name="see-also"></a>Zobacz też

[Windows:: Foundation — przestrzeń nazw](windows-foundation-namespace.md)
