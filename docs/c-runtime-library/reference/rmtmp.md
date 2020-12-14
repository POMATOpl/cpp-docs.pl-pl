---
description: 'Dowiedz się więcej na temat: _rmtmp'
title: _rmtmp
ms.date: 4/2/2020
api_name:
- _rmtmp
- _o__rmtmp
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _rmtmp
helpviewer_keywords:
- removing temporary files
- _rmtmp function
- files [C++], temporary
- rmtmp function
- files [C++], removing
- temporary files [C++], removing
ms.assetid: 7419501e-2587-4f2a-b469-0dca07f84736
ms.openlocfilehash: fd87dd407b2e392d197e7eb407bc307b48ea2263
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250195"
---
# <a name="_rmtmp"></a>_rmtmp

Usuwa pliki tymczasowe.

## <a name="syntax"></a>Składnia

```C

int _rmtmp( void );
```

## <a name="return-value"></a>Wartość zwracana

**_rmtmp** zwraca liczbę plików tymczasowych zamkniętych i usuniętych.

## <a name="remarks"></a>Uwagi

Funkcja **_rmtmp** czyści wszystkie pliki tymczasowe w bieżącym katalogu. Funkcja usuwa tylko te pliki, które zostały utworzone przez **tmpfile**; Użyj go tylko w tym samym katalogu, w którym zostały utworzone pliki tymczasowe.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_rmtmp**|\<stdio.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Przykład

Zobacz przykład dla [tmpfile](tmpfile.md).

## <a name="see-also"></a>Zobacz też

[We/Wy strumienia](../../c-runtime-library/stream-i-o.md)<br/>
[_flushall](flushall.md)<br/>
[tmpfile](tmpfile.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
