---
description: 'Dowiedz się więcej na temat: &lt; &gt; funkcje list'
title: '&lt;&gt;funkcje list | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::swap
ms.openlocfilehash: 6a94fcc916db08a510a968b66b0a0dc0cfa9b8e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284710"
---
# <a name="ltlistgt-functions"></a>&lt;&gt;funkcje list

## <a name="swap"></a><a name="swap"></a> wymiany

Wymienia elementy dwóch list.

```cpp
template <class T, class Allocator>
    void swap(list<T, Allocator>& left, list<T, Allocator>& right)
```

### <a name="parameters"></a>Parametry

*lewym*\
Obiekt typu `list`.

*Kliknij*\
Obiekt typu `list`.

### <a name="remarks"></a>Uwagi

Ta funkcja szablonu jest wykonywana `left.swap(right)` .
