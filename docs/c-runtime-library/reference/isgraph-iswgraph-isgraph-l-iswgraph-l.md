---
description: 'Dowiedz się więcej na temat: isgraph, iswgraph, _isgraph_l, _iswgraph_l'
title: isgraph, iswgraph, _isgraph_l, _iswgraph_l
ms.date: 4/2/2020
api_name:
- isgraph
- iswgraph
- _iswgraph_l
- _isgraph_l
- _o_isgraph
- _o_iswgraph
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _isgraph_l
- _iswgraph_l
- Isgraph
- _istgraph_l
- _istgraph
- iswgraph
helpviewer_keywords:
- isgraph function
- _istgraph_l function
- istgraph function
- _isgraph_l function
- iswgraph function
- _iswgraph_l function
- _istgraph function
- _ismbcgraph_l function
ms.assetid: 531a5f34-4302-4d0a-8a4f-b7ea150ad941
ms.openlocfilehash: 165972af4c921abb9026c6a3297426910cbf49e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332677"
---
# <a name="isgraph-iswgraph-_isgraph_l-_iswgraph_l"></a>isgraph, iswgraph, _isgraph_l, _iswgraph_l

Określa, czy liczba całkowita reprezentuje znak graficzny.

## <a name="syntax"></a>Składnia

```C
int isgraph(
   int c
);
int iswgraph(
   wint_t c
);
int _isgraph_l(
   int c,
   _locale_t locale
);
int _iswgraph_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametry

*s*<br/>
Liczba całkowita do przetestowania.

## <a name="return-value"></a>Wartość zwracana

Każda z tych procedur zwraca wartość różną od zera, jeśli *c* jest szczególną reprezentacją znaku drukowalnego innego niż spacja. **isgraph** zwraca wartość różną od zera, jeśli *c* jest znakiem drukowalnym innym niż spacja. **iswgraph** zwraca wartość różną od zera, jeśli *c* jest drukowalnym znakiem dwubajtowym innym niż spacja. Każda z tych procedur zwraca wartość 0, jeśli *c* nie spełnia warunku testu.

Wersje tych funkcji, które mają sufiks **_l** używają ustawień regionalnych, które zostały przesłane zamiast bieżących ustawień regionalnych dla zachowań zależnych od ustawień regionalnych. Aby uzyskać więcej informacji, zobacz [Ustawienia regionalne](../../c-runtime-library/locale.md).

Zachowanie obiektu **isgraph** i **_isgraph_l** jest niezdefiniowane, jeśli *c* nie jest typu EOF lub z zakresu od 0 do 0xFF włącznie. Gdy jest używana Biblioteka CRT debugowania, a *c* nie jest jedną z tych wartości, funkcje zgłaszają potwierdzenie.

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura TCHAR.H|Nie zdefiniowano _MBCS _UNICODE &|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istgraph**|**isgraf**|[_ismbcgraph](ismbcgraph-functions.md)|**iswgraph**|
|**_istgraph_l**|**_isgraph_l**|[_ismbcgraph_l](ismbcgraph-functions.md)|**_iswgraph_l**|

## <a name="remarks"></a>Uwagi

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**isgraf**|\<ctype.h>|
|**iswgraph**|\<ctype.h> lub \<wchar.h>|
|**_isgraph_l**|\<ctype.h>|
|**_iswgraph_l**|\<ctype.h> lub \<wchar.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Klasyfikacja znaków](../../c-runtime-library/character-classification.md)<br/>
[Ustawienie](../../c-runtime-library/locale.md)<br/>
[to, ISW, procedury](../../c-runtime-library/is-isw-routines.md)<br/>
