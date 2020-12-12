---
description: 'Dowiedz się więcej na temat: &lt; Operatory przydzielania &gt;'
title: '&lt;&gt;Operatory przytwórców'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: a0289ca7b76aaddb2e6c8ed20a58a61d1be40998
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163473"
---
# <a name="ltallocatorsgt-operators"></a>&lt;&gt;Operatory przytwórców

Są to funkcje operatora szablonu globalnego zdefiniowane w przystawce &lt; &gt; . Aby uzyskać funkcje operatora składowej klasy, zobacz dokumentację klasy.

[operator! =](#op_neq)\
[operator = =](#op_eq_eq)

## <a name="operator"></a><a name="op_neq"></a> operator! =

Testuje pod kątem nierówności pomiędzy obiektami alokatora określonej klasy.

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Jeden z obiektów alokatora, który ma być testowany pod kątem nierówności.

*Kliknij*\
Jeden z obiektów alokatora, który ma być testowany pod kątem nierówności.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli obiekty programu przydzielania nie są równe; **`false`** Jeśli obiekty alokatora są równe.

### <a name="remarks"></a>Uwagi

Operator szablonu zwraca wartość `!(left == right)` .

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

Testuje pod kątem równości pomiędzy obiektami alokatora określonej klasy.

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Jeden z obiektów alokatora, który ma być testowany pod kątem równości.

*Kliknij*\
Jeden z obiektów alokatora, który ma być testowany pod kątem równości.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli obiekty alokatora są równe; **`false`** Jeśli obiekty alokatora nie są równe.

### <a name="remarks"></a>Uwagi

Ten operator szablonu zwraca wartość `left.equals(right)` .

## <a name="see-also"></a>Zobacz też

[\<allocators>](allocators-header.md)
