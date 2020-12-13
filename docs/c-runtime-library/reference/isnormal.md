---
description: 'Dowiedz się więcej o: isnormal'
title: isnormal
ms.date: 01/31/2019
f1_keywords:
- isnormal
- math/isnormal
helpviewer_keywords:
- isnormal function
ms.openlocfilehash: 3afae5196a7a6b2b149028ad347f95baa27b1544
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337759"
---
# <a name="isnormal"></a>isnormal

Określa, czy wartość zmiennoprzecinkowa jest wartością normalną.

## <a name="syntax"></a>Składnia

```C
int isnormal(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isnormal(
   FloatingType x
) throw(); /* C++-only function template */
```

### <a name="parameters"></a>Parametry

*x*<br/>
Wartość zmiennoprzecinkowa do przetestowania.

## <a name="return-value"></a>Wartość zwracana

Funkcja **isnormal** zwraca wartość różną od zera ( **`true`** w kodzie C++), jeśli argument *x* nie jest zerem, subnormal, Infinity ani NaN. W przeciwnym razie funkcja **isnormal** zwraca wartość 0 ( **`false`** w kodzie C++).

## <a name="remarks"></a>Uwagi

**isnormal** to makro skompilowane jako C i szablon wbudowanej funkcji w przypadku skompilowania jako C++.

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek (C)|Wymagany nagłówek (C++)|
|--------------|---------------------------|-------------------------------|
|**isnormal**|\<math.h>|\<math.h> lub \<cmath>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf —](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
