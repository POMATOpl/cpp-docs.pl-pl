---
description: 'Dowiedz się więcej na temat: _com_ptr_t:: Release'
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: a1b81295ab249b1826ea6d373f782d91765df3b7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344721"
---
# <a name="_com_ptr_trelease"></a>_com_ptr_t::Release

**Specyficzne dla firmy Microsoft**

Wywołuje funkcję elementu członkowskiego **Zwolnij** `IUnknown` na wskaźniku hermetyzowanego interfejsu.

## <a name="syntax"></a>Składnia

```cpp
void Release( );
```

## <a name="remarks"></a>Uwagi

Wywołuje `IUnknown::Release` na hermetyzowanym wskaźniku interfejsu, wywołując `E_POINTER` błąd, jeśli ten wskaźnik interfejsu ma wartość null.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_ptr_t](../cpp/com-ptr-t-class.md)
