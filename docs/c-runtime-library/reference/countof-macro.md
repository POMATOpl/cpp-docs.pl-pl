---
title: _countof Macro | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apilocation:
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
apitype: DLLExport
f1_keywords:
- _countof
- countof
dev_langs:
- C++
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 773cf37e3a9e3d7047f0de4cd489c0ae9f41f61d
ms.sourcegitcommit: 604907f77eb6c5b1899194a9877726f3e8c2dabc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/28/2018
---
# <a name="countof-macro"></a>_countof — Makro

Oblicza liczbę elementów w tablicy statycznie przydzielone.

## <a name="syntax"></a>Składnia

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>Parametry

*Tablica*<br/>
Nazwa tablicy.

## <a name="return-value"></a>Wartość zwracana

Liczba elementów w tablicy, wyrażony jako **size_t**.

## <a name="remarks"></a>Uwagi

`_countof` jest implementowany jako preprocesor makra przypominającej funkcji. Wersja języka C++ ma dodatkowy szablon maszyny do wykrywania w czasie kompilacji, jeśli wskaźnik jest przekazywany zamiast statycznie zadeklarowanych tablicy.

Upewnij się, że *tablicy* jest rzeczywiście tablicy, nie wskaźnik. W języku C `_countof` tworzy błędne wyniki, jeśli *tablicy* wskaźnik. W języku C++ `_countof` kompilacji Jeśli *tablicy* wskaźnik.  Tablica przekazany jako parametr do funkcji *decays do wskaźnika*, co oznacza, że w funkcji, nie można użyć `_countof` do ustalenia zakresu tablicy.

## <a name="requirements"></a>Wymagania

|Macro|Wymagany nagłówek|
|-----------|---------------------|
|`_countof`|\<stdlib.h>|

## <a name="example"></a>Przykład

```cpp
// crt_countof.cpp
#define _UNICODE
#include <stdio.h>
#include <stdlib.h>
#include <tchar.h>

int main( void )
{
   _TCHAR arr[20], *p;
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );
   // In C++, the following line would generate a compile-time error:
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)

   _tcscpy_s( arr, _countof(arr), _T("a string") );
   // unlike sizeof, _countof works here for both narrow- and wide-character strings
}
```

```Output
sizeof(arr) = 40 bytes
_countof(arr) = 20 elements
```

## <a name="see-also"></a>Zobacz także

[sizeof, operator](../../cpp/sizeof-operator.md)<br/>
