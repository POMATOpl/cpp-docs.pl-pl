---
title: towctrans — | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- towctrans
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- towctrans
dev_langs:
- C++
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9d70570339868feb62ee906a707cf16ca03d556
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407632"
---
# <a name="towctrans"></a>towctrans

Przekształca znak.

## <a name="syntax"></a>Składnia

```C
wint_t towctrans(
   wint_t c,
   wctrans_t category
);
```

### <a name="parameters"></a>Parametry

*c*<br/>
Znak, który ma być transformacji.

*category*<br/>
Identyfikator, który zawiera wartość zwracaną [wctrans —](wctrans.md).

## <a name="return-value"></a>Wartość zwracana

Znak *c*, po **towctrans —** używać reguł przekształcania w *kategorii*.

## <a name="remarks"></a>Uwagi

Wartość *kategorii* musi zwrócony przez wcześniej pomyślne wywołanie [wctrans —](wctrans.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**towctrans**|\<wctype.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

Zobacz **wctrans —** dla przykładu korzystającego z **towctrans —**.

## <a name="see-also"></a>Zobacz także

[Konwersja danych](../../c-runtime-library/data-conversion.md)<br/>
