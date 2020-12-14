---
description: 'Dowiedz się więcej na temat: Podnosiexception funkcja'
title: RaiseException — Funkcja
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
ms.openlocfilehash: b5353757ff04ab12c0fc61da6b2e98b2df835ef0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198443"
---
# <a name="raiseexception-function"></a>RaiseException — Funkcja

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
inline void __declspec(noreturn)   RaiseException(
      HRESULT hr,
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);
```

### <a name="parameters"></a>Parametry

*godz.*<br/>
Kod wyjątku dla zgłoszonego wyjątku; oznacza to, że HRESULT operacji zakończonej niepowodzeniem.

*dwExceptionFlags*<br/>
Flaga wskazująca ciągły wyjątek (wartość flagi to zero) lub wyjątek nieciągły (wartość flagi jest różna od zera). Domyślnie wyjątek nie jest ciągły.

## <a name="remarks"></a>Uwagi

Wywołuje wyjątek w wątku wywołującym.

Aby uzyskać więcej informacji, zobacz funkcja systemu Windows `RaiseException` .

## <a name="requirements"></a>Wymagania

**Nagłówek:** Internal. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL::D etails — przestrzeń nazw](microsoft-wrl-details-namespace.md)
