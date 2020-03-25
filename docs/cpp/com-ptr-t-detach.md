---
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: 8ba42f19e3474cc4a3199771f761b021221f430e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190017"
---
# <a name="_com_ptr_tdetach"></a>_com_ptr_t::Detach

**Specyficzne dla firmy Microsoft**

Wyodrębnia i zwraca wskaźnik interfejsu hermetyzowanego.

## <a name="syntax"></a>Składnia

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>Uwagi

Wyodrębnia i zwraca wskaźnik interfejsu hermetyzowanego, a następnie czyści pamięć hermetyzowaną wskaźnika do wartości NULL. Spowoduje to usunięcie wskaźnika interfejsu z hermetyzacji. Jest to możliwe do wywołania `Release` na zwróconym wskaźniku interfejsu.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[_com_ptr_t, klasa](../cpp/com-ptr-t-class.md)
