---
description: 'Dowiedz się więcej o: _countof makro'
title: _countof — Makro
ms.date: 03/22/2018
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _countof
- countof
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
ms.openlocfilehash: 190f47aa7bb6bcf6bbd9478cce9df90aca81b437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146461"
---
# <a name="_countof-macro"></a>_countof — Makro

Oblicza liczbę elementów w tablicy, która jest przydzieloną statycznie.

## <a name="syntax"></a>Składnia

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>Parametry

*array*<br/>
Nazwa tablicy.

## <a name="return-value"></a>Wartość zwracana

Liczba elementów w tablicy wyrażona jako **size_t**.

## <a name="remarks"></a>Uwagi

**_countof** jest zaimplementowana jako makro preprocesora podobne do funkcji. Wersja języka C++ ma dodatkowe maszyny szablonu do wykrycia w czasie kompilacji, jeśli wskaźnik jest przenoszona zamiast tablicy zadeklarowanej statycznie.

Upewnij się, że *Tablica* jest w rzeczywistości tablicą, a nie wskaźnikiem. W języku C, **_countof** generuje błędne wyniki, jeśli *Tablica* jest wskaźnikiem. W języku C++ **_countof** kompilacja nie powiedzie się, jeśli *Tablica* jest wskaźnikiem.  Tablica przenoszona jako parametr do funkcji powoduje *zanik wskaźnika*, co oznacza, że w funkcji nie można użyć **_countof** , aby określić zakres tablicy.

## <a name="requirements"></a>Wymagania

|Makro|Wymagany nagłówek|
|-----------|---------------------|
|**_countof**|\<stdlib.h>|

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

[sizeof — Operator](../../cpp/sizeof-operator.md)<br/>
