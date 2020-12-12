---
description: 'Dowiedz się więcej na temat: funkcja CreateActivationFactory —'
title: CreateActivationFactory — Funkcja
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
ms.openlocfilehash: 25f2181a00bb018361b05ea6570ebbadc6f7a975
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273111"
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory — Funkcja

Tworzy fabrykę, która tworzy wystąpienia określonej klasy, które mogą być aktywowane przez środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```cpp
template<typename Factory>
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,
      REFIID riid,
   _Outptr_ IUnknown **ppFactory) throw();
```

### <a name="parameters"></a>Parametry

*znaczników*<br/>
Kombinacja co najmniej jednej wartości wyliczenia [RuntimeClassType —](runtimeclasstype-enumeration.md) .

*Autotekstu*<br/>
Wskaźnik do [CreatorMap](creatormap-structure.md) , który zawiera informacje o inicjacji i rejestracji parametru *riid*.

*riid*<br/>
Odwołanie do identyfikatora interfejsu.

*ppFactory*<br/>
Jeśli ta operacja zakończy się pomyślnie, wskaźnik do fabryki aktywacji.

## <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wynik HRESULT wskazuje na błąd.

## <a name="remarks"></a>Uwagi

Błąd potwierdzenia jest emitowany, jeśli *fabryka* parametrów szablonu nie pochodzi od interfejsu `IActivationFactory` .

## <a name="requirements"></a>Wymagania

**Nagłówek:** module. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL:: otoki::D etails przestrzeń nazw](microsoft-wrl-wrappers-details-namespace.md)
