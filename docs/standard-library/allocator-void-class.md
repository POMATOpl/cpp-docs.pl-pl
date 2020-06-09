---
title: '&lt;Klasa void programu przydzielania &gt;'
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: af29c70dca56b1e68eef3614357269c587a77ec9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623680"
---
# <a name="allocatorltvoidgt-class"></a>&lt;Klasa void programu przydzielania &gt;

Specjalizacja alokatora szablonu klasy do typu **void**, definiując typy, które mają sens w tym kontekście.

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

Klasa jawnie wyspecjalizowany [Alokator](allocator-class.md) szablonu klasy dla typu **void**. Jego konstruktory i operator przypisania zachowują się tak samo jak dla szablonu klasy, ale definiuje tylko następujące typy:

- [const_pointer](allocator-class.md#const_pointer).

- [wskaźnik](allocator-class.md#pointer).

- [value_type](allocator-class.md#value_type).

- ponownie [powiązać](allocator-class.md#rebind)szablon klasy zagnieżdżonej.
