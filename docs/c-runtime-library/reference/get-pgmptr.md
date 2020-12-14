---
description: 'Dowiedz się więcej na temat: _get_pgmptr'
title: _get_pgmptr
ms.date: 4/2/2020
api_name:
- _get_pgmptr
- _o__get_pgmptr
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_pgmptr
- _get_pgmptr
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
ms.openlocfilehash: 440bc7221f00d5ce04f4583666a76a0fadfee288
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296592"
---
# <a name="_get_pgmptr"></a>_get_pgmptr

Pobiera bieżącą wartość **_pgmptr** zmiennej globalnej.

## <a name="syntax"></a>Składnia

```C
errno_t _get_pgmptr(
   char **pValue
);
```

### <a name="parameters"></a>Parametry

*pValue*<br/>
Wskaźnik do ciągu, który ma zostać wypełniony bieżącą wartością zmiennej **_pgmptr** .

## <a name="return-value"></a>Wartość zwracana

Zwraca zero, jeśli pomyślne; kod błędu w przypadku niepowodzenia. Jeśli *pValue* ma **wartość null**, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, ta funkcja ustawia **errno** na **EINVAL** i zwraca **EINVAL**.

## <a name="remarks"></a>Uwagi

Wywołaj **_get_pgmptr** tylko wtedy, gdy program ma wąski punkt wejścia, taki jak **Main ()** lub **WinMain ()**. **_Pgmptr** zmienna globalna zawiera pełną ścieżkę do pliku wykonywalnego skojarzonego z procesem. Aby uzyskać więcej informacji, zobacz [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_get_pgmptr**|\<stdlib.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[_get_wpgmptr](get-wpgmptr.md)<br/>
