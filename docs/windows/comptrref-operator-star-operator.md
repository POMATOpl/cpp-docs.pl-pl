---
title: Operator ComPtrRef::operator * | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator*
dev_langs:
- C++
helpviewer_keywords:
- operator* operator
ms.assetid: 0287ca7a-4ce1-47f7-bab6-714fca3e04bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5bb6bc06f65f53f919197b5350db8aacc268013f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602962"
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator* Operator

Obsługuje infrastrukturę biblioteki WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
InterfaceType* operator *();
```

## <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu, reprezentowane przez bieżącą **comptrref —** obiektu.

## <a name="remarks"></a>Uwagi

Pobiera wskaźnik do interfejsu, reprezentowane przez bieżącą **comptrref —** obiektu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Zobacz też

[ComPtrRef, klasa](../windows/comptrref-class.md)  
[Microsoft::WRL::Details, przestrzeń nazw](../windows/microsoft-wrl-details-namespace.md)