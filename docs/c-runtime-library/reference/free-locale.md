---
title: _free_locale
ms.date: 11/04/2016
api_name:
- _free_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __free_locale
- free_locale
- _free_locale
helpviewer_keywords:
- __free_locale function
- free_locale function
- locales, freeing
- _free_locale function
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
ms.openlocfilehash: 31a8e3191c5e370acb00aaf12e21f0c712c51dd1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956749"
---
# <a name="_free_locale"></a>_free_locale

Zwalnia obiekt ustawień regionalnych.

## <a name="syntax"></a>Składnia

```C
void _free_locale(
   _locale_t locale
);
```

### <a name="parameters"></a>Parametry

*ustawienie*<br/>
Obiekt ustawień regionalnych do zwolnienia.

## <a name="remarks"></a>Uwagi

Funkcja **_free_locale** służy do zwalniania obiektu ustawień regionalnych uzyskanych z wywołania **_get_current_locale** lub **_create_locale**.

Poprzednia nazwa tej funkcji, **__free_locale** (z dwoma wiodącymi podkreśleniami), jest przestarzała.

## <a name="requirements"></a>Wymagania

|**Procedury**|Wymagany nagłówek|
|---------------|---------------------|
|**_free_locale**|\<locale.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz także

[_get_current_locale](get-current-locale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
