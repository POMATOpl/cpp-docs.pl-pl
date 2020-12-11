---
description: 'Dowiedz się więcej o: &lt; wszystkie &gt; funkcje'
title: '&lt;wszystkie &gt; funkcje'
ms.date: 04/04/2019
f1_keywords:
- any/std::any_cast
- any/std::make_any
- any/std::swap
ms.openlocfilehash: 03f699ac5c48962bb32a604a885bc0b3c60c8b22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163395"
---
# <a name="ltanygt-functions"></a>&lt;wszystkie &gt; funkcje

## <a name="any_cast"></a><a name="any_cast"></a> any_cast

Sprawia, że obiekt jest dowolna.

```cpp
template<class T>
    T any_cast(const any& operand);
template<class T>
    T any_cast(any& operand);
template<class T>
    T any_cast(any&& operand);
template<class T>
    const T* any_cast(const any* operand) noexcept;
template<class T>
    T* any_cast(any* operand) noexcept;
```

## <a name="make_any"></a><a name="make_any"></a> make_any

Pobiera wartości i tworzy dowolny obiekt.

```cpp
template <class T, class... Args>
    any make_any(Args&& ...args);
template <class T, class U, class... Args>
    any make_any(initializer_list<U> il, Args&& ...args);
```

## <a name="swap"></a><a name="swap"></a> wymiany

Wymienia elementy dwóch obiektów.

```cpp
void swap(any& left, any& right) noexcept;
```

### <a name="parameters"></a>Parametry

*lewym*\
Obiekt typu `any`.

*Kliknij*\
Obiekt typu `any`.
