---
description: 'Dowiedz się więcej na temat: _cexit, _c_exit'
title: _cexit, _c_exit
ms.date: 4/2/2020
api_name:
- _c_exit
- _cexit
- _o__cexit
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
- _cexit
- c_exit
- _c_exit
- cexit
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
ms.openlocfilehash: e901e7d7e37c8702efaae8b3b70e98a400f48ef1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275103"
---
# <a name="_cexit-_c_exit"></a>_cexit, _c_exit

Wykonuje operacje czyszczenia i zwraca bez zakończenia procesu.

## <a name="syntax"></a>Składnia

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>Uwagi

Funkcja **_cexit** wywołuje, w kolejności ostatniej-w, pierwszy-out (LIFO), funkcje zarejestrowane przez **atexit —** i **_onexit**. Następnie **_cexit** opróżnia wszystkie bufory we/wy i zamyka wszystkie otwarte strumienie przed zwróceniem. **_c_exit** jest taka sama jak **_exit** , ale powraca do procesu wywołującego bez przetwarzania buforów strumieni **atexit —** lub **_onexit** ani opróżniania. W poniższej tabeli przedstawiono zachowanie funkcji **Exit**, **_exit**, **_cexit** i **_c_exit** .

|Funkcja|Zachowanie|
|--------------|--------------|
|**Opuść**|Wykonuje kompletne procedury kończenia biblioteki C, kończy proces i kończy pracę z dostarczonym kodem stanu.|
|**_exit**|Wykonuje szybkie procedury kończenia biblioteki C, kończy proces i kończy pracę z dostarczonym kodem stanu.|
|**_cexit**|Wykonuje kompletne procedury kończenia biblioteki C i powraca do obiektu wywołującego, ale nie kończy procesu.|
|**_c_exit**|Wykonuje szybkie procedury kończenia biblioteki C i powraca do obiektu wywołującego, ale nie kończy procesu.|

Po wywołaniu funkcji **_cexit** lub **_c_exit** , destruktory dla wszelkich obiektów tymczasowych lub automatycznych, które istnieją w czasie wywołania nie są wywoływane. Obiekt automatyczny jest obiektem, który jest zdefiniowany w funkcji, w której obiekt nie został zadeklarowany jako statyczny. Obiekt tymczasowy jest obiektem utworzonym przez kompilator. Aby zniszczyć obiekt automatyczny przed wywołaniem **_cexit** lub **_c_exit**, jawnie Wywołaj destruktor dla obiektu w następujący sposób:

```cpp
myObject.myClass::~myClass( );
```

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Proces i kontrola środowiska](../../c-runtime-library/process-and-environment-control.md)<br/>
[przerwij](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, funkcje _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, funkcje _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
