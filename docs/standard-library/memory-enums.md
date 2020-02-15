---
title: '&lt;wyliczeń&gt; pamięci'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 78cdb0fe6c0d9487500804d21fe4ad4870fcad0f
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257835"
---
# <a name="ltmemorygt-enums"></a>&lt;wyliczeń&gt; pamięci

## <a name="pointer_safety"></a>pointer_safety, Wyliczenie

Wyliczenie możliwych wartości zwracanych przez `get_pointer_safety`.

```cpp
class pointer_safety {
   relaxed,
   preferred,
   strict
};
```

### <a name="remarks"></a>Uwagi

**Wyliczenie** w zakresie definiuje wartości, które mogą być zwracane przez `get_pointer_safety()`:

`relaxed`--wskaźniki nie są bezpiecznie wyprowadzane (oczywiście wskaźniki do zadeklarowanych lub przyznanych obiektów) są traktowane jak te, które bezpiecznie pochodzą.

`preferred`--tak jak wcześniej, ale wskaźniki, które nie są bezpiecznie wyprowadzane, nie należy wywoływać.

`strict` — wskaźniki, które nie są bezpiecznie wyprowadzane, mogą być traktowane inaczej niż te, które są bezpiecznie wyprowadzane.
