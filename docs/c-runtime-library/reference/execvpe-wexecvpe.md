---
description: 'Dowiedz się więcej na temat: _execvpe, _wexecvpe'
title: _execvpe, _wexecvpe
ms.date: 4/2/2020
api_name:
- _execvpe
- _wexecvpe
- _o__execvpe
- _o__wexecvpe
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wexecvpe
- _wexecvpe
- _execvpe
helpviewer_keywords:
- wexecvpe function
- execvpe function
- _wexecvpe function
- _execvpe function
ms.assetid: c0c3c986-d9c0-4814-a96c-10f0b3092766
ms.openlocfilehash: d2a9baf9e39335c47a10d7c5f7e8baa8484bee66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236103"
---
# <a name="_execvpe-_wexecvpe"></a>_execvpe, _wexecvpe

Ładuje i uruchamia nowe procesy podrzędne.

> [!IMPORTANT]
> Tego interfejsu API nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows. Aby uzyskać więcej informacji, zobacz [funkcje CRT nieobsługiwane w aplikacjach platforma uniwersalna systemu Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Składnia

```C
intptr_t _execvpe(
   const char *cmdname,
   const char *const *argv,
   const char *const *envp
);
intptr_t _wexecvpe(
   const wchar_t *cmdname,
   const wchar_t *const *argv,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>Parametry

*cmdname*<br/>
Ścieżka pliku do wykonania.

*argv*<br/>
Tablica wskaźników do parametrów.

*envp*<br/>
Tablica wskaźników do ustawień środowiska.

## <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, te funkcje nie zwracają do procesu wywołującego. Zwracana wartość-1 wskazuje błąd, w którym to przypadku jest ustawiona zmienna globalna **errno** .

|**errno** wartość|Opis|
|-------------------|-----------------|
|**E2BIG**|Miejsce wymagane dla argumentów i ustawień środowiska przekracza 32 KB.|
|**EACCES**|Określony plik ma naruszenie zasad blokowania lub udostępniania.|
|**EMFILE**|Zbyt wiele plików jest otwartych. (Określony plik musi być otwarty, aby określić, czy jest to plik wykonywalny).|
|**ENOENT**|Nie znaleziono pliku lub ścieżki.|
|**ENOEXEC**|Określony plik nie jest wykonywalny lub ma nieprawidłowy format pliku wykonywalnego.|
|**ENOMEM**|Za mało dostępnej pamięci do wykonania nowego procesu; dostępna pamięć została uszkodzona; lub istnieje nieprawidłowy blok, który wskazuje, że proces wywołujący nie został poprawnie przydzielony.|

Aby uzyskać więcej informacji na temat tych i innych kodów powrotnych, zobacz [errno, _doserrno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Uwagi

Każda z tych funkcji ładuje i uruchamia nowy proces i przekazuje tablicę wskaźników do argumentów wiersza polecenia oraz tablicę wskaźników do ustawień środowiska. Te funkcje używają zmiennej środowiskowej **Path** , aby znaleźć plik do wykonania.

Funkcje **_execvpe** sprawdzają poprawność swoich parametrów. Jeśli *cmdname* jest wskaźnikiem typu null lub jeśli *argv* jest wskaźnikiem typu null, wskaźnikiem do pustej tablicy lub wskaźnikiem do tablicy zawierającej pusty ciąg jako pierwszy argument, te funkcje wywołują procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, te funkcje ustawiają **errno** na **EINVAL** i Return-1. Żaden proces nie jest uruchamiany.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|Opcjonalny nagłówek|
|--------------|---------------------|---------------------|
|**_execvpe**|\<process.h>|\<errno.h>|
|**_wexecvpe**|\<process.h> lub \<wchar.h>|\<errno.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

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
