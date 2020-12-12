---
description: 'Dowiedz się więcej na temat: Klasa alokatora &lt; void &gt;'
title: '&lt;Klasa void programu przydzielania &gt;'
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: a6468c35f4660736cd297ffd7ae3d0738bbf0756
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163512"
---
# <a name="allocatorltvoidgt-class"></a>&lt;Klasa void programu przydzielania &gt;

Specjalizacja alokatora szablonu klasy do typu **`void`** , definiując typy, które mają sens w tym kontekście.

## <a name="syntax"></a>Składnia

```cpp
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```

## <a name="remarks"></a>Uwagi

Klasa jawnie wyspecjalizowany [Alokator](allocator-class.md) szablonu klasy dla typu **`void`** . Jego konstruktory i operator przypisania zachowują się tak samo jak dla szablonu klasy, ale definiuje tylko następujące typy:

- [const_pointer](allocator-class.md#const_pointer).

- [wskaźnik](allocator-class.md#pointer).

- [value_type](allocator-class.md#value_type).

- ponownie [powiązać](allocator-class.md#rebind)szablon klasy zagnieżdżonej.
