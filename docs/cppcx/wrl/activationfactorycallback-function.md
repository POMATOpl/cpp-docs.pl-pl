---
description: 'Dowiedz się więcej na temat: funkcja ActivationFactoryCallback —'
title: ActivationFactoryCallback — Funkcja
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
ms.openlocfilehash: 9398b3f681e32c7a73b46de549ce7c41a3af6196
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204618"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback — Funkcja

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(
   HSTRING activationId,
   IActivationFactory **ppFactory
);
```

### <a name="parameters"></a>Parametry

*activationId — Członek*<br/>
Dojście do ciągu, który określa nazwę klasy środowiska uruchomieniowego.

*ppFactory*<br/>
Po zakończeniu tej operacji fabryka aktywacji odpowiada parametrowi *activationId — Członek*.

## <a name="return-value"></a>Wartość zwracana

S_OK, jeśli się to powiedzie; w przeciwnym razie wartość HRESULT, która opisuje awarię. Możliwe niepowodzenia HRESULT to CLASS_E_CLASSNOTAVAILABLE i E_INVALIDARG.

## <a name="remarks"></a>Uwagi

Pobiera fabrykę aktywacji dla określonego identyfikatora aktywacji.

Środowisko wykonawcze systemu Windows wywołuje tę funkcję wywołania zwrotnego, aby zażądać obiektu określonego przez jego nazwę klasy środowiska uruchomieniowego.

## <a name="requirements"></a>Wymagania

**Nagłówek:** module. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL::D etails — przestrzeń nazw](microsoft-wrl-details-namespace.md)
