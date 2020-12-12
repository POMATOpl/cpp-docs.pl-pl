---
description: Dowiedz się więcej na temat klasy is_lvalue_reference
title: is_lvalue_reference — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_lvalue_reference
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
ms.openlocfilehash: 624849bce456048f4454542db8a03f37771a46d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230904"
---
# <a name="is_lvalue_reference-class"></a>is_lvalue_reference — Klasa

Testuje, czy typ jest odwołaniem lvalue.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_lvalue_reference;
```

### <a name="parameters"></a>Parametry

*Br*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie tego predykatu typu ma wartość true, jeśli typ *ty* jest odwołaniem do obiektu lub funkcji, w przeciwnym razie ma wartość false. Zwróć uwagę, że *ty* nie może być odwołaniem do rvalue. Aby uzyskać więcej informacji na temat rvalues, zobacz [rvalue Reference deklarator:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[Lvalues i rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)
