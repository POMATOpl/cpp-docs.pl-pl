---
title: '&lt;scoped_allocator&gt; operatory | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
dev_langs:
- C++
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: c2c61e3fce5d1cf58f59bc9dd51920bccc0eb2f3
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966475"
---
# <a name="ltscopedallocatorgt-operators"></a>&lt;scoped_allocator&gt; operatorów

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator! =

Testuje dwa `scoped_allocator_adaptor` obiekty pod kątem nierówności.

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Parametry

*po lewej stronie* po lewej stronie `scoped_allocator_adaptor` obiektu.

*prawy* po prawej stronie `scoped_allocator_adaptor` obiektu.

### <a name="return-value"></a>Wartość zwracana

`!(left == right)`

## <a name="op_eq_eq"></a>  operator ==

Testuje dwa `scoped_allocator_adaptor` obiekty pod kątem równości.

```cpp
template <class Outer, class... Inner>
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>Parametry

*po lewej stronie* po lewej stronie `scoped_allocator_adaptor` obiektu.

*prawy* po prawej stronie `scoped_allocator_adaptor` obiektu.

### <a name="return-value"></a>Wartość zwracana

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>Zobacz także

[<scoped_allocator>](../standard-library/scoped-allocator.md)<br/>
