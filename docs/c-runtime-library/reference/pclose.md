---
description: 'Dowiedz się więcej na temat: _pclose'
title: _pclose
ms.date: 4/2/2020
api_name:
- _pclose
- _o__pclose
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
- _pclose
- pclose
helpviewer_keywords:
- _pclose function
- pclose function
- pipes, closing
ms.assetid: e2e31a9e-ba3a-4124-bcbb-c4040110b3d3
ms.openlocfilehash: 529af8ccdd1c6cc27f9039adef5d75c8b977aa54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258710"
---
# <a name="_pclose"></a>_pclose

Czeka na nowy procesor poleceń i zamyka strumień na skojarzonym potoku.

> [!IMPORTANT]
> Tego interfejsu API nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows. Aby uzyskać więcej informacji, zobacz [funkcje CRT nieobsługiwane w aplikacjach platforma uniwersalna systemu Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Składnia

```C
int _pclose(
FILE *stream
);
```

### <a name="parameters"></a>Parametry

*produkcyjne*<br/>
Wartość zwracana z poprzedniego wywołania do **_popen**.

## <a name="return-value"></a>Wartość zwracana

Zwraca stan zakończenia procesora poleceń kończących lub-1, jeśli wystąpi błąd. Format wartości zwracanej jest taki sam, jak w przypadku **_cwait**, z wyjątkiem tego, że zamienione są małe i wysokie kolejności bajtów. Jeśli strumień ma **wartość null**, **_pclose** ustawia **errno** na **EINVAL** i zwraca wartość-1.

Aby uzyskać informacje o tych i innych kodach błędów, zobacz [_doserrno, errno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Uwagi

Funkcja **_pclose** wyszukuje identyfikator procesu procesora poleceń (Cmd.exe) uruchomionego przez skojarzone wywołanie **_popen** , wykonuje wywołanie [_cwait](cwait.md) w nowym procesorze poleceń i zamyka strumień w skojarzonym potoku.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_pclose**|\<stdio.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Zobacz też

[Proces i kontrola środowiska](../../c-runtime-library/process-and-environment-control.md)<br/>
[_pipe](pipe.md)<br/>
[_popen, _wpopen](popen-wpopen.md)<br/>
