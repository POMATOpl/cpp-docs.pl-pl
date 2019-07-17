---
title: '&lt;cwchar —&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cwchar>
helpviewer_keywords:
- cwchar header
ms.assetid: 7380b1bf-a220-46e5-b832-9f9f4e543aac
ms.openlocfilehash: 8a82a821ab8cb705b6244b2763f3f0b022c0e3e5
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243634"
---
# <a name="ltcwchargt"></a>&lt;cwchar —&gt;

Dołącza nagłówek biblioteki standardowej C \<wchar.h > i dodaje skojarzone nazwy `std` przestrzeni nazw.

## <a name="syntax"></a>Składnia

```cpp
#include <cwchar>
```

## <a name="remarks"></a>Uwagi

Dołączenie tego pliku nagłówkowego gwarantuje również, że nazwy zadeklarowane przez zewnętrzne powiązanie w nagłówku standardowej biblioteki C są deklarowane w `std` przestrzeni nazw.

## <a name="constants"></a>Stałe

```cpp
namespace std {
    using size_t = see below;
    using mbstate_t = see below ;
    using wint_t = see below ;
}

#define NULL see below
#define WCHAR_MAX see below
#define WCHAR_MIN see below
#define WEOF see below
```

## <a name="structs"></a>Struktury

```cpp
struct tm;
```

## <a name="functions"></a>Funkcje

```cpp
int fwprintf(FILE* stream, const wchar_t* format, ...);
int fwscanf(FILE* stream, const wchar_t* format, ...);
int swprintf(wchar_t* s, size_t n, const wchar_t* format, ...);
int swscanf(const wchar_t* s, const wchar_t* format, ...);
int vfwprintf(FILE* stream, const wchar_t* format, va_list arg);
int vfwscanf(FILE* stream, const wchar_t* format, va_list arg);
int vswprintf(wchar_t* s, size_t n, const wchar_t* format, va_list arg);
int vswscanf(const wchar_t* s, const wchar_t* format, va_list arg);
int vwprintf(const wchar_t* format, va_list arg);
int vwscanf(const wchar_t* format, va_list arg);
int wprintf(const wchar_t* format, ...);
int wscanf(const wchar_t* format, ...);
wint_t fgetwc(FILE* stream);
wchar_t* fgetws(wchar_t* s, int n, FILE* stream);
wint_t fputwc(wchar_t c, FILE* stream);
int fputws(const wchar_t* s, FILE* stream);
int fwide(FILE* stream, int mode);
wint_t getwc(FILE* stream);
wint_t getwchar();
wint_t putwc(wchar_t c, FILE* stream);
wint_t putwchar(wchar_t c);
wint_t ungetwc(wint_t c, FILE* stream);
double wcstod(const wchar_t* nptr, wchar_t** endptr);
float wcstof(const wchar_t* nptr, wchar_t** endptr);
long double wcstold(const wchar_t* nptr, wchar_t** endptr);
long int wcstol(const wchar_t* nptr, wchar_t** endptr, int base);
long long int wcstoll(const wchar_t* nptr, wchar_t** endptr, int base);
unsigned long int wcstoul(const wchar_t* nptr, wchar_t** endptr, int base);
unsigned long long int wcstoull(const wchar_t* nptr, wchar_t** endptr, int base);
wchar_t* wcscpy(wchar_t* s1, const wchar_t* s2);
wchar_t* wcsncpy(wchar_t* s1, const wchar_t* s2, size_t n);
wchar_t* wmemcpy(wchar_t* s1, const wchar_t* s2, size_t n);
wchar_t* wmemmove(wchar_t* s1, const wchar_t* s2, size_t n);
wchar_t* wcscat(wchar_t* s1, const wchar_t* s2);
wchar_t* wcsncat(wchar_t* s1, const wchar_t* s2, size_t n);
int wcscmp(const wchar_t* s1, const wchar_t* s2);
int wcscoll(const wchar_t* s1, const wchar_t* s2);
int wcsncmp(const wchar_t* s1, const wchar_t* s2, size_t n);
size_t wcsxfrm(wchar_t* s1, const wchar_t* s2, size_t n);
int wmemcmp(const wchar_t* s1, const wchar_t* s2, size_t n);
const wchar_t* wcschr(const wchar_t* s, wchar_t c) // see 20.2
wchar_t* wcschr(wchar_t* s, wchar_t c) // see 20.2
size_t wcscspn(const wchar_t* s1, const wchar_t* s2);
const wchar_t* wcspbrk(const wchar_t* s1, const wchar_t* s2) // see 20.2
wchar_t* wcspbrk(wchar_t* s1, const wchar_t* s2) // see 20.2
const wchar_t* wcsrchr(const wchar_t* s, wchar_t c) // see 20.2
wchar_t* wcsrchr(wchar_t* s, wchar_t c) // see 20.2
size_t wcsspn(const wchar_t* s1, const wchar_t* s2);
const wchar_t* wcsstr(const wchar_t* s1, const wchar_t* s2) // see 20.2
wchar_t* wcsstr(wchar_t* s1, const wchar_t* s2) // see 20.2
wchar_t* wcstok(wchar_t* s1, const wchar_t* s2, wchar_t** ptr);
const wchar_t* wmemchr(const wchar_t* s, wchar_t c, size_t n) // see 20.2
wchar_t* wmemchr(wchar_t* s, wchar_t c, size_t n) // see 20.2
size_t wcslen(const wchar_t* s);
wchar_t* wmemset(wchar_t* s, wchar_t c, size_t n);
size_t wcsftime(wchar_t* s, size_t maxsize, const wchar_t* format, const struct tm* timeptr);
wint_t btowc(int c);
int wctob(wint_t c);
// 24.5.6, multibyte / wide string and character conversion functions
int mbsinit(const mbstate_t* ps);
size_t mbrlen(const char* s, size_t n, mbstate_t* ps);
size_t mbrtowc(wchar_t* pwc, const char* s, size_t n, mbstate_t* ps);
size_t wcrtomb(char* s, wchar_t wc, mbstate_t* ps);
size_t mbsrtowcs(wchar_t* dst, const char** src, size_t len, mbstate_t* ps);
size_t wcsrtombs(char* dst, const wchar_t** src, size_t len, mbstate_t* ps);
```

## <a name="see-also"></a>Zobacz także

[Odwołanie do plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)<br/>
[Standardowa biblioteka C++ — przegląd](../standard-library/cpp-standard-library-overview.md)<br/>
[Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
