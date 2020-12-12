---
description: 'Dowiedz się więcej na temat: funkcja GetActivationFactory —'
title: GetActivationFactory — Funkcja
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
ms.openlocfilehash: ae2384e0620282723c6f10090a0028347408b271
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124634"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory — Funkcja

Pobiera fabrykę aktywacji dla typu określonego przez parametr szablonu.

## <a name="syntax"></a>Składnia

```cpp
template<typename T>
inline HRESULT GetActivationFactory(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory
);
```

### <a name="parameters"></a>Parametry

*T*<br/>
Parametr szablonu, który określa typ fabryki aktywacji.

*Wpisy*<br/>
Nazwa klasy, którą może wygenerować fabryka aktywacji.

*indywidual*<br/>
Po zakończeniu tej operacji odwołanie do fabryki aktywacji dla typu *T*.

## <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie błąd HRESULT wskazujący Dlaczego ta operacja nie powiodła się.

## <a name="requirements"></a>Wymagania

**Nagłówek:** Client. h

**Przestrzeń nazw:** Windows:: Foundation

## <a name="see-also"></a>Zobacz też

[Windows:: Foundation — przestrzeń nazw](windows-foundation-namespace.md)
