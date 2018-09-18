---
title: ___lc_locale_name_func | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- ___lc_locale_name_func
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- ___lc_locale_name_func
dev_langs:
- C++
helpviewer_keywords:
- ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb94b73bf3f32c61fae37f7d3c9b9c51d012bfb6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087919"
---
# <a name="lclocalenamefunc"></a>___lc_locale_name_func

Wewnętrzny funkcji CRT. Pobiera nazwę ustawień regionalnych bieżącego wątku.

## <a name="syntax"></a>Składnia

```cpp
wchar_t** ___lc_locale_name_func(void);
```

## <a name="return-value"></a>Wartość zwracana

Wskaźnik do ciągu, który zawiera nazwę ustawień regionalnych bieżącego wątku.

## <a name="remarks"></a>Uwagi

`___lc_locale_name_func` jest wewnętrzny funkcji CRT, który jest używany przez inne funkcje CRT, można uzyskać z magazynu lokalnego wątku CRT data bieżąca nazwa ustawień regionalnych. Te informacje są dostępne również za pomocą [_get_current_locale —](../c-runtime-library/reference/get-current-locale.md) funkcji lub [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) funkcji.

Wewnętrzne funkcje CRT są specyficzne dla implementacji i może ulec zmianie z każdej wersji. Nie zalecamy ich użycie w kodzie.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|`___lc_locale_name_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Zobacz też

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)