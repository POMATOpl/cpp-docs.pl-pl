---
description: 'Dowiedz się więcej na temat: przyrostowe operatory C i zmniejszanie'
title: Operatory przyrostka inkrementacji i dekrementacji języka C
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
ms.openlocfilehash: e5e230f1e1e51a1f48b29436705f4f645be9ed44
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300219"
---
# <a name="c-postfix-increment-and-decrement-operators"></a>Operatory przyrostka inkrementacji i dekrementacji języka C

Operandy przyrostka przyrostkowego i zmniejszania są typami skalarnymi, które są modyfikowane l-wartości.

## <a name="syntax"></a>Składnia

*wyrażenie przyrostkowe*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie przyrostkowe*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie przyrostkowe*  **--**

Wynikiem operacji przyrostka przyrostkowego lub zmniejszania jest wartość operandu. Po uzyskaniu wyniku wartość operandu jest zwiększana (lub zmniejszana). Poniższy kod ilustruje przyrostowy operator przyrostu.

```
if( var++ > 0 )
    *p++ = *q++;
```

W tym przykładzie zmienna `var` jest porównywana z wartością 0, a następnie zwiększana. Jeśli `var` była wynikiem dodatnim przed zwiększeniem wartości, następna instrukcja zostanie wykonana. Najpierw wartość obiektu wskazywanego przez `q` jest przypisana do obiektu wskazywanego przez `p` . Następnie `q` i `p` są zwiększane.

## <a name="see-also"></a>Zobacz też

[Operatory przyrostka i zmniejszenie: + + i--](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)
