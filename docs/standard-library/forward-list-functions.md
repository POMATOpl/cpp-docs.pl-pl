---
description: Dowiedz się więcej na temat &lt; &gt; funkcji forward_list
title: '&lt;&gt;funkcje forward_list'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 3f827b777f2e6fa62dd78c7d737d5da84b50610c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324370"
---
# <a name="ltforward_listgt-functions"></a>&lt;&gt;funkcje forward_list

## <a name="swap"></a><a name="swap"></a> wymiany

Wymienia elementy dwóch list do przodu.

```cpp
void swap(forward_list <Type, Allocator>& left, forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Obiekt typu `forward_list`.

*Kliknij*\
Obiekt typu `forward_list`.

### <a name="remarks"></a>Uwagi

Ta funkcja szablonu jest wykonywana `left.swap(right)` .
