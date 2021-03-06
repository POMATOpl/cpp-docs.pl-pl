---
description: 'Dowiedz się więcej na temat: funkcja TerminateMap —'
title: TerminateMap — Funkcja
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: 919759d0b4b7f67cf3aff83c3e83678860d0badc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135066"
---
# <a name="terminatemap-function"></a>TerminateMap — Funkcja

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()
```

### <a name="parameters"></a>Parametry

*elementu*<br/>
[Moduł](module-class.md).

*serverName*<br/>
Nazwa podzbioru fabryk klasy w module określonym przez *moduł* parametrów.

*forceTerminate*<br/>
**`true`** do kończenia fabryk klas niezależnie od ich aktywności. **`false`** nie należy kończyć fabryk klas, jeśli jakakolwiek fabryka jest aktywna.

## <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli wszystkie fabryki klas zostały zakończone; w przeciwnym razie **`false`** .

## <a name="remarks"></a>Uwagi

Zamyka fabryki klas w określonym module.

## <a name="requirements"></a>Wymagania

**Nagłówek:** module. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL::D etails — przestrzeń nazw](microsoft-wrl-details-namespace.md)
