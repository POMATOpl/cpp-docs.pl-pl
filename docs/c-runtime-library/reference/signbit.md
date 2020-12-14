---
description: 'Dowiedz się więcej na temat: signbit —'
title: signbit
ms.date: 01/31/2019
f1_keywords:
- signbit
- math/signbit
helpviewer_keywords:
- signbit function
ms.openlocfilehash: 7f6416647db67a49bd6950c011575b72f4c43f10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303469"
---
# <a name="signbit"></a>signbit

Określa, czy wartość zmiennoprzecinkowa jest ujemna.

## <a name="syntax"></a>Składnia

```C
int signbit(
   /* floating-point */ x
); /* C-only macro */

inline bool signbit(
   float x
) throw(); /* C++-only overloaded function */

inline bool signbit(
   double x
) throw(); /* C++-only overloaded function */

inline bool signbit(
   long double x
) throw(); /* C++-only overloaded function */
```

### <a name="parameters"></a>Parametry

*x*<br/>
Wartość zmiennoprzecinkowa do przetestowania.

## <a name="return-value"></a>Wartość zwracana

**signbit —** zwraca wartość różną od zera ( **`true`** w języku C++), jeśli argument *x* jest ujemny lub ujemny. Zwraca wartość 0 ( **`false`** w języku C++), jeśli argument jest nieujemny, nieskończoności dodatniej lub NaN.

## <a name="remarks"></a>Uwagi

**signbit —** jest makrem kompilowanym jako C i przeciążoną funkcją wbudowaną kompilowaną jako C++.

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek (C)|Wymagany nagłówek (C++)|
|--------------|---------------------------|-------------------------------|
|**signbit**|\<math.h>|\<math.h> lub \<cmath>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf —](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
