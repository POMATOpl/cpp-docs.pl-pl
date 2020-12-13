---
description: Dowiedz się więcej na temat struktury nullopt_t
title: Struktura nullopt_t
ms.date: 08/04/2019
f1_keywords:
- optional/std::nullopt_t
- optional/std::nullopt
ms.openlocfilehash: 7a597dcc5f15843f125dc7572dc4c5694320f0bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338114"
---
# <a name="nullopt_t-struct"></a>Struktura nullopt_t

`nullopt_t`Typ jest unikatowym, pustym typem używanym do wskazania, że obiekt [opcjonalny](optional-class.md) nie zawiera wartości.

Stała `nullopt` typu wskazuje, że `nullopt_t` `optional` Typ ma niezainicjowany stan. Może służyć do inicjowania `optional` obiektu lub porównywania z jednym.

## <a name="syntax"></a>Składnia

```cpp
struct nullopt_t;
inline constexpr nullopt_t nullopt{ /*implementation-defined*/ };
```

## <a name="see-also"></a>Zobacz też

[\<optional>](optional.md)\
[optional, klasa](optional-class.md)
