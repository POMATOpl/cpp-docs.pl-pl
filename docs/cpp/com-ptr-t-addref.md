---
description: 'Dowiedz się więcej na temat: _com_ptr_t:: AddRef'
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 0979245662a94596307b1a63af918d0ce67c7b6f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295695"
---
# <a name="_com_ptr_taddref"></a>_com_ptr_t::AddRef

**Specyficzne dla firmy Microsoft**

Wywołuje `AddRef` funkcję elementu członkowskiego `IUnknown` na wyhermetyzowanym wskaźniku interfejsu.

## <a name="syntax"></a>Składnia

```cpp
void AddRef( );
```

## <a name="remarks"></a>Uwagi

Wywołuje `IUnknown::AddRef` na hermetyzowanym wskaźniku interfejsu, wywołując `E_POINTER` błąd, jeśli wskaźnik ma wartość null.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_ptr_t](../cpp/com-ptr-t-class.md)
