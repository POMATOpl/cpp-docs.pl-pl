---
description: 'Dowiedz się więcej na temat: wctype'
title: wctype
ms.date: 11/04/2016
api_name:
- wctype
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctype
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
ms.openlocfilehash: 0791d4f048dfa5d6804db14d577b1370ffbf8754
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254199"
---
# <a name="wctype"></a>wctype

Określa regułę klasyfikacji dla kodów szerokich znaków.

## <a name="syntax"></a>Składnia

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>Parametry

*wartość*<br/>
Ciąg właściwości.

## <a name="return-value"></a>Wartość zwracana

Jeśli kategoria **LC_CTYPE** bieżących ustawień regionalnych nie definiuje reguły klasyfikacji, której nazwa jest zgodna z *właściwością* String, funkcja zwraca wartość zero. W przeciwnym razie zwraca wartość różną od zera odpowiednią do użycia jako drugi argument dla kolejnego wywołania do [towctrans](towctrans.md).

## <a name="remarks"></a>Uwagi

Funkcja Określa regułę klasyfikacji dla kodów szerokich znaków. Poniższe pary wywołań mają takie samo zachowanie we wszystkich ustawieniach regionalnych (ale implementacja może definiować dodatkowe reguły klasyfikacji nawet w ustawieniach regionalnych "C"):

|Funkcja|Tak samo jak|
|--------------|-------------|
|iswalnum (c)|iswctype (c, wctype ("alnum"))|
|iswalpha (c)|iswctype (c, wctype ("alfa"))|
|iswcntrl (c)|iswctype (c, wctype ("cntrl"))|
|iswdigit (c)|iswctype (c, wctype ("cyfra"))|
|iswgraph (c)|iswctype (c, wctype ("Graph"))|
|iswlower (c)|iswctype (c, wctype ("Lower"))|
|iswprint (c)|iswctype (c, wctype ("Print")|
|iswpunct (c)|iswctype (c, wctype ("punct"))|
|iswspace (c)|iswctype (c, wctype ("Space"))|
|iswupper (c)|iswctype (c, wctype ("Upper"))|
|iswxdigit (c)|iswctype (c, wctype ("xdigit"))|

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Konwersja danych](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
