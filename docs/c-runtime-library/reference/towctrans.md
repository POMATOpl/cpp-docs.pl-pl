---
description: 'Dowiedz się więcej na temat: towctrans'
title: towctrans
ms.date: 11/04/2016
api_name:
- towctrans
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- towctrans
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
ms.openlocfilehash: 7b8ecdd38ca45eb658d5e9f61bf05549878228bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318302"
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

*s*<br/>
Znak, który ma zostać przekształcony.

*kategorii*<br/>
Identyfikator, który zawiera wartość zwracaną z [wctrans](wctrans.md).

## <a name="return-value"></a>Wartość zwracana

Znak *c*, po **towctrans** użył reguły przekształcania w *kategorii*.

## <a name="remarks"></a>Uwagi

Wartość *kategorii* musi być zwrócona przez wcześniejsze pomyślne wywołanie do [wctrans](wctrans.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**towctrans**|\<wctype.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

Zobacz **wctrans** , aby uzyskać przykład, który korzysta z **towctrans**.

## <a name="see-also"></a>Zobacz też

[Konwersja danych](../../c-runtime-library/data-conversion.md)<br/>
