---
title: '&lt;cstring&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstring>
helpviewer_keywords:
- <cstring> header
- cstring header
ms.assetid: d665429f-5d39-4712-9c0a-68c8abcc3536
ms.openlocfilehash: cc6821d63a42d498347745bb7a96c838fc634415
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246619"
---
# <a name="ltcstringgt"></a>&lt;cstring&gt;

Dołącza nagłówek biblioteki standardowej C \<string.h > i dodaje skojarzone nazwy `std` przestrzeni nazw.

## <a name="syntax"></a>Składnia

```cpp
#include <cstring>
```

## <a name="remarks"></a>Uwagi

Dołączenie tego pliku nagłówkowego gwarantuje również, że nazwy zadeklarowane przez zewnętrzne powiązanie w nagłówku standardowej biblioteki C są deklarowane w `std` przestrzeni nazw.

## <a name="constants"></a>Stałe

```cpp
namespace std {
    using size_t = see below;
}

#define NULL
```

## <a name="functions"></a>Funkcje

```cpp
void* memcpy(void* s1, const void* s2, size_t n);
void* memmove(void* s1, const void* s2, size_t n);
char* strcpy(char* s1, const char* s2);
char* strncpy(char* s1, const char* s2, size_t n);
char* strcat(char* s1, const char* s2);
char* strncat(char* s1, const char* s2, size_t n);
int memcmp(const void* s1, const void* s2, size_t n);
int strcmp(const char* s1, const char* s2);
int strcoll(const char* s1, const char* s2);
int strncmp(const char* s1, const char* s2, size_t n);
size_t strxfrm(char* s1, const char* s2, size_t n);
const void* memchr(const void* s, int c, size_t n); // see 20.2
void* memchr(void* s, int c, size_t n) // see 20.2
const char* strchr(const char* s, int c) // see 20.2
char* strchr(char* s, int c) // see 20.2
size_t strcspn(const char* s1, const char* s2);
const char* strpbrk(const char* s1, const char* s2) // see 20.2
char* strpbrk(char* s1, const char* s2) // see 20.2
const char* strrchr(const char* s, int c) // see 20.2
char* strrchr(char* s, int c) // see 20.2
size_t strspn(const char* s1, const char* s2);
const char* strstr(const char* s1, const char* s2) // see 20.2
char* strstr(char* s1, const char* s2) // see 20.2
char* strtok(char* s1, const char* s2);
void* memset(void* s, int c, size_t n);
char* strerror(int errnum);
size_t strlen(const char* s);
```

## <a name="see-also"></a>Zobacz także

[Odwołanie do plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)<br/>
[Standardowa biblioteka C++ — przegląd](../standard-library/cpp-standard-library-overview.md)<br/>
[Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
