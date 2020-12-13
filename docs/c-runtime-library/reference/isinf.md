---
description: 'Dowiedz się więcej na temat: isinf —'
title: isinf
ms.date: 01/31/2019
f1_keywords:
- isinf
- math/isinf
helpviewer_keywords:
- isinf function
ms.openlocfilehash: f174855ddbb8cc43fd7338d4254c0f03bf53967d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332647"
---
# <a name="isinf"></a>isinf

Określa, czy wartość zmiennoprzecinkowa jest nieskończonością.

## <a name="syntax"></a>Składnia

```C
int isinf(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isinf(
   FloatingType x
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>Parametry

*x*<br/>
Wartość zmiennoprzecinkowa do przetestowania.

## <a name="return-value"></a>Wartość zwracana

**isinf —** zwraca wartość różną od zera ( **`true`** w kodzie C++), jeśli argument *x* jest nieskończoną dodatnią lub ujemną. **isinf —** zwraca wartość 0 ( **`false`** w kodzie C++), jeśli argument jest skończona lub NaN. Normalne i nienormalne wartości zmiennoprzecinkowe są uważane za skończone.

## <a name="remarks"></a>Uwagi

**isinf —** to makro, które jest kompilowane jako C i wbudowana funkcja szablonu po skompilowaniu jako C++.

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek (C)|Wymagany nagłówek (C++)|
|--------------|---------------------------|-------------------------------|
|**isinf —**|\<math.h>|\<math.h> lub \<cmath>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
