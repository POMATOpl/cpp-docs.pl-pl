---
description: 'Dowiedz się więcej na temat: Wielowątkowość i ustawienia regionalne'
title: Wielowątkowość i ustawienia regionalne
ms.date: 11/04/2016
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
ms.openlocfilehash: 246eb6c9be7046a77770de701d15754579b66055
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149984"
---
# <a name="multithreading-and-locales"></a>Wielowątkowość i ustawienia regionalne

Biblioteka środowiska uruchomieniowego C i Standardowa biblioteka języka C++ zapewniają obsługę zmiany ustawień regionalnych programu. W tym temacie omówiono problemy, które powstają w przypadku korzystania z funkcji regionalnych obu bibliotek w aplikacji wielowątkowej.

## <a name="remarks"></a>Uwagi

Biblioteka środowiska uruchomieniowego języka C umożliwia tworzenie aplikacji wielowątkowych za pomocą `_beginthread` `_beginthreadex` funkcji i. Ten temat dotyczy tylko aplikacji wielowątkowych utworzonych przy użyciu tych funkcji. Aby uzyskać więcej informacji, zobacz [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md).

Aby zmienić ustawienia regionalne przy użyciu biblioteki środowiska uruchomieniowego języka C, użyj funkcji [setlocals](../preprocessor/setlocale.md) . W poprzednich wersjach Visual C++ ta funkcja zawsze modyfikuje ustawienia regionalne całej aplikacji. Obecnie obsługujemy Ustawianie ustawień regionalnych dla poszczególnych wątków. W tym celu należy użyć funkcji [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) . Aby określić, że [setlocale](../preprocessor/setlocale.md) powinno zmienić tylko ustawienia regionalne w bieżącym wątku, wywołaj `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` w tym wątku. W przeciwnym razie wywołanie `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` spowoduje, że ten wątek będzie używał globalnych ustawień regionalnych, a każde wywołanie metody [setlocaling](../preprocessor/setlocale.md) w tym wątku zmieni ustawienia regionalne we wszystkich wątkach, które nie mają jawnie włączonej ustawień regionalnych dla wątku.

Aby zmienić ustawienia regionalne przy użyciu biblioteki środowiska uruchomieniowego języka C++, użyj [klasy locale](../standard-library/locale-class.md). Wywołując metodę [locale:: Global](../standard-library/locale-class.md#global) , należy zmienić ustawienia regionalne we wszystkich wątkach, które nie są jawnie włączone dla ustawień regionalnych poszczególnych wątków. Aby zmienić ustawienia regionalne w pojedynczym wątku lub części aplikacji, po prostu Utwórz wystąpienie `locale` obiektu w tym wątku lub części kodu.

> [!NOTE]
> Wywoływanie [ustawień regionalnych:: Global](../standard-library/locale-class.md#global) zmienia ustawienia regionalne dla standardowej biblioteki C++ i biblioteki środowiska uruchomieniowego języka C. Jednak wywołanie metody [setlocal](../preprocessor/setlocale.md) powoduje jedynie zmianę ustawień regionalnych dla biblioteki środowiska uruchomieniowego języka C. nie dotyczy to biblioteki standardowej języka C++.

W poniższych przykładach pokazano, jak używać funkcji [setlocale](../preprocessor/setlocale.md) , [klasy locale](../standard-library/locale-class.md)i funkcji [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) , aby zmienić ustawienia regionalne aplikacji w kilku różnych scenariuszach.

## <a name="example-change-locale-with-per-thread-locale-enabled"></a>Przykład: Zmień ustawienia regionalne z włączonymi ustawieniami regionalnymi dla poszczególnych wątków

W tym przykładzie wątek główny duplikuje dwa wątki podrzędne. Pierwszy wątek, wątek A, włącza ustawienia regionalne dla wątku przez wywołanie `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . Drugi wątek, wątek B, a także główny wątek nie należy włączać ustawień regionalnych poszczególnych wątków. Następnie wątek A następnie zmienia ustawienia regionalne przy użyciu funkcji [setlocaling](../preprocessor/setlocale.md) biblioteki środowiska uruchomieniowego języka C.

Ponieważ wątek A ma włączone ustawienia regionalne dla wątku, tylko funkcja biblioteki środowiska uruchomieniowego języka C w wątku A zaczyna korzystanie z ustawień regionalnych "francuski". Biblioteka środowiska uruchomieniowego języka C w wątku B i w wątku głównym nadal używa ustawień regionalnych "C". Ponadto, ponieważ [setlocaling](../preprocessor/setlocale.md) nie ma wpływu na ustawienia regionalne standardowej biblioteki języka c++, wszystkie obiekty biblioteki standardowej c++ nadal używają ustawień regionalnych "C".

```cpp
// multithread_locale_1.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    setlocale(LC_ALL, "french");
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "French_France.1252"
[Thread A] locale::global is set to "C"

[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "C"
[Thread B] locale::global is set to "C"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "C"
[Thread main] locale::global is set to "C"
```

## <a name="example-change-global-locale-with-per-thread-locale-enabled"></a>Przykład: Zmień globalne ustawienia regionalne z włączonymi ustawieniami regionalnymi dla poszczególnych wątków

W tym przykładzie wątek główny duplikuje dwa wątki podrzędne. Pierwszy wątek, wątek A, włącza ustawienia regionalne dla wątku przez wywołanie `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . Drugi wątek, wątek B, a także główny wątek nie należy włączać ustawień regionalnych poszczególnych wątków. Następnie wątek A następnie zmienia ustawienia regionalne przy użyciu metody [locale:: Global](../standard-library/locale-class.md#global) biblioteki standardowej języka C++.

Ponieważ wątek A ma włączone ustawienia regionalne dla wątku, tylko funkcja biblioteki środowiska uruchomieniowego języka C w wątku A zaczyna korzystanie z ustawień regionalnych "francuski". Biblioteka środowiska uruchomieniowego języka C w wątku B i w wątku głównym nadal używa ustawień regionalnych "C". Jednak ponieważ metoda [locale:: Global](../standard-library/locale-class.md#global) zmienia ustawienia regionalne "Globally", wszystkie obiekty standardowej biblioteki C++ we wszystkich wątkach zaczynają się od ustawień regionalnych "francuski".

```cpp
// multithread_locale_2.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    locale::global(locale("french"));
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "French_France.1252"
[Thread A] locale::global is set to "French_France.1252"

[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "C"
[Thread B] locale::global is set to "French_France.1252"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "C"
[Thread main] locale::global is set to "French_France.1252"
```

## <a name="example-change-locale-without-per-thread-locale-enabled"></a>Przykład: Zmień ustawienia regionalne bez włączonej ustawień regionalnych dla wątku

W tym przykładzie wątek główny duplikuje dwa wątki podrzędne. Pierwszy wątek, wątek A, włącza ustawienia regionalne dla wątku przez wywołanie `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . Drugi wątek, wątek B, a także główny wątek nie należy włączać ustawień regionalnych poszczególnych wątków. Wątek B następnie zmienia ustawienia regionalne przy użyciu funkcji [setlocaling](../preprocessor/setlocale.md) biblioteki środowiska uruchomieniowego języka C.

Ponieważ w wątku B nie włączono ustawień regionalnych dla wątku, biblioteka środowiska uruchomieniowego języka C działa w wątku B i w wątku głównym rozpoczyna się przy użyciu ustawień regionalnych "francuski". Biblioteka środowiska uruchomieniowego języka C działa w wątku A kontynuuje Używanie ustawień regionalnych "C", ponieważ wątek A ma włączone ustawienia regionalne dla wątku. Ponadto, ponieważ [setlocaling](../preprocessor/setlocale.md) nie ma wpływu na ustawienia regionalne standardowej biblioteki języka c++, wszystkie obiekty biblioteki standardowej c++ nadal używają ustawień regionalnych "C".

```cpp
// multithread_locale_3.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
BOOL configThreadLocaleCalled = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    configThreadLocaleCalled = TRUE;
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!configThreadLocaleCalled)
        Sleep(100);
    setlocale(LC_ALL, "french");
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "French_France.1252"
[Thread B] locale::global is set to "C"

[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "C"
[Thread A] locale::global is set to "C"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "French_France.1252"
[Thread main] locale::global is set to "C"
```

## <a name="example-change-global-locale-without-per-thread-locale-enabled"></a>Przykład: Zmień globalne ustawienia regionalne bez włączonej ustawień regionalnych dla wątku

W tym przykładzie wątek główny duplikuje dwa wątki podrzędne. Pierwszy wątek, wątek A, włącza ustawienia regionalne dla wątku przez wywołanie `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . Drugi wątek, wątek B, a także główny wątek nie należy włączać ustawień regionalnych poszczególnych wątków. Wątek B następnie zmienia ustawienia regionalne przy użyciu metody [locale:: Global](../standard-library/locale-class.md#global) biblioteki standardowej języka C++.

Ponieważ w wątku B nie włączono ustawień regionalnych dla wątku, biblioteka środowiska uruchomieniowego języka C działa w wątku B i w wątku głównym rozpoczyna się przy użyciu ustawień regionalnych "francuski". Biblioteka środowiska uruchomieniowego języka C działa w wątku A kontynuuje Używanie ustawień regionalnych "C", ponieważ wątek A ma włączone ustawienia regionalne dla wątku. Jednak ponieważ metoda [locale:: Global](../standard-library/locale-class.md#global) zmienia ustawienia regionalne "Globally", wszystkie obiekty standardowej biblioteki C++ we wszystkich wątkach zaczynają się od ustawień regionalnych "francuski".

```cpp
// multithread_locale_4.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
BOOL configThreadLocaleCalled = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    configThreadLocaleCalled = TRUE;
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!configThreadLocaleCalled)
        Sleep(100);
    locale::global(locale("french"));
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "French_France.1252"
[Thread B] locale::global is set to "French_France.1252"

[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "C"
[Thread A] locale::global is set to "French_France.1252"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "French_France.1252"
[Thread main] locale::global is set to "French_France.1252"
```

## <a name="see-also"></a>Zobacz też

[Obsługa wielowątkowości w przypadku starszego kodu (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)<br/>
[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)<br/>
[_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)<br/>
[setlocale](../preprocessor/setlocale.md)<br/>
[Internacjonalizacja](../c-runtime-library/internationalization.md)<br/>
[Ustawienie](../c-runtime-library/locale.md)<br/>
[\<clocale>](../standard-library/clocale.md)<br/>
[\<locale>](../standard-library/locale.md)<br/>
[locale — Klasa](../standard-library/locale-class.md)
