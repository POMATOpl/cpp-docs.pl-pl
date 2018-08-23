---
title: SyncLockWithStatusT::IsLocked, metoda | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d70a2c316f9e7994292f3dc29cef5bce993778ad
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595066"
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked — Metoda

Obsługuje infrastrukturę biblioteki WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
bool IsLocked() const;
```

## <a name="remarks"></a>Uwagi

Wskazuje, czy bieżący **synclockwithstatust —** obiekt posiada zasób; czyli, **synclockwithstatust —** obiekt jest *zablokowane*.

## <a name="return-value"></a>Wartość zwracana

**wartość true,** Jeśli **synclockwithstatust —** obiektu jest zablokowany; w przeciwnym razie **false**.

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Zobacz też

[SyncLockWithStatusT, klasa](../windows/synclockwithstatust-class.md)