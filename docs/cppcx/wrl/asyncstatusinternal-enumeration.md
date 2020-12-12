---
description: 'Dowiedz się więcej o: AsyncStatusInternal — Enumeration'
title: AsyncStatusInternal — Wyliczenie
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: 3227699a0e7b8933dc5839e65fb3489328d3b1f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175797"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal — Wyliczenie

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>Uwagi

Określa mapowanie między wyliczeniami wewnętrznymi dla stanu operacji asynchronicznych i `Windows::Foundation::AsyncStatus` wyliczenia.

## <a name="members"></a>Elementy członkowskie

`_Created`<br/>
Równoważne `::Windows::Foundation::AsyncStatus::Created`

`_Started`<br/>
Równoważne `::Windows::Foundation::AsyncStatus::Started`

`_Completed`<br/>
Równoważne `::Windows::Foundation::AsyncStatus::Completed`

`_Cancelled`<br/>
Równoważne `::Windows::Foundation::AsyncStatus::Cancelled`

`_Error`<br/>
Równoważne `::Windows::Foundation::AsyncStatus::Error`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Async. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL::D etails — przestrzeń nazw](microsoft-wrl-details-namespace.md)
