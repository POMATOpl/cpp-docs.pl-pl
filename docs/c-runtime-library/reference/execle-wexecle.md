---
description: 'Dowiedz się więcej na temat: _execle, _wexecle'
title: _execle, _wexecle
ms.date: 11/04/2016
api_name:
- _execle
- _wexecle
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
- api-ms-win-crt-process-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wexecle
- _execle
- _wexecle
helpviewer_keywords:
- wexecle function
- execle function
- _wexecle function
- _execle function
ms.assetid: 75efa9c5-96b7-4e23-acab-06258901f63a
ms.openlocfilehash: 28e05222d0ee91f44f96717056117a67afe5c0b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304899"
---
# <a name="_execle-_wexecle"></a>_execle, _wexecle

Ładuje i wykonuje nowe procesy podrzędne.

> [!IMPORTANT]
> Tego interfejsu API nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows. Aby uzyskać więcej informacji, zobacz [funkcje CRT nieobsługiwane w aplikacjach platforma uniwersalna systemu Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Składnia

```C
intptr_t _execle(
   const char *cmdname,
   const char *arg0,
   ... const char *argn,
   NULL,
   const char *const *envp
);
intptr_t _wexecle(
   const wchar_t *cmdname,
   const wchar_t *arg0,
   ... const wchar_t *argn,
   NULL,
   const char *const *envp
);
```

### <a name="parameters"></a>Parametry

*cmdname*<br/>
Ścieżka pliku do wykonania.

*arg0*,... *argN*<br/>
Lista wskaźników do parametrów.

*envp*<br/>
Tablica wskaźników do ustawień środowiska.

## <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, te funkcje nie zwracają do procesu wywołującego. Zwracana wartość-1 wskazuje błąd, w którym to przypadku jest ustawiona zmienna globalna **errno** .

|**errno** wartość|Opis|
|-------------------|-----------------|
|**E2BIG**|Miejsce, które jest wymagane dla argumentów i ustawień środowiska, przekracza 32 KB.|
|**EACCES**|Określony plik ma naruszenie zasad blokowania lub udostępniania.|
|**EINVAL**|Nieprawidłowy parametr.|
|**EMFILE**|Zbyt wiele plików jest otwartych. (Określony plik musi być otwarty, aby określić, czy jest to plik wykonywalny).|
|**ENOENT**|Nie znaleziono pliku lub ścieżki.|
|**ENOEXEC**|Określony plik nie jest wykonywalny lub ma nieprawidłowy format pliku wykonywalnego.|
|**ENOMEM**|Za mało dostępnej pamięci do wykonania nowego procesu; dostępna pamięć została uszkodzona; lub istnieje nieprawidłowy blok, który wskazuje, że proces wywołujący nie został poprawnie przydzielony.|

Aby uzyskać więcej informacji na temat tych kodów powrotnych, zobacz [_doserrno, errno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Uwagi

Każda z tych funkcji ładuje i uruchamia nowy proces i przekazuje każdy argument wiersza polecenia jako oddzielny parametr i przekazuje tablicę wskaźników do ustawień środowiska.

Funkcje **_execle** sprawdzają poprawność swoich parametrów. Jeśli *cmdname* lub *arg0* jest wskaźnikiem o wartości null lub pustym ciągiem, te funkcje wywołują procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, te funkcje ustawiają **errno** na **EINVAL** i Return-1. Żaden nowy proces nie jest uruchamiany.

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|Opcjonalny nagłówek|
|--------------|---------------------|---------------------|
|**_execle**|\<process.h>|\<errno.h>|
|**_wexecle**|\<process.h> lub \<wchar.h>|\<errno.h>|

Aby uzyskać więcej informacji, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

Zobacz przykład w [_exec, _Wexec Functions](../../c-runtime-library/exec-wexec-functions.md).

## <a name="see-also"></a>Zobacz też

[Proces i kontrola środowiska](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, funkcje _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[przerwij](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, funkcje _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
