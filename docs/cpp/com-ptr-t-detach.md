---
description: 'Dowiedz się więcej na temat: _com_ptr_t::D etach'
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: ec2a18a04b8c32e373225235fd0d6f520e768af0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295513"
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

[Klasa _com_ptr_t](../cpp/com-ptr-t-class.md)
