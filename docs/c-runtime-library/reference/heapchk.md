---
description: 'Dowiedz się więcej na temat: _heapchk'
title: _heapchk
ms.date: 4/2/2020
api_name:
- _heapchk
- _o__heapchk
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _heapchk
- heapchk
helpviewer_keywords:
- debugging [CRT], heap-related problems
- consistency checking of heaps
- heapchk function
- heaps, checking consistency
- _heapchk function
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
ms.openlocfilehash: 57cde789c8d6e6b8c8da91adf4a6f274ce557ed7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332795"
---
# <a name="_heapchk"></a>_heapchk

Uruchamia sprawdzanie spójności sterty.

## <a name="syntax"></a>Składnia

```C
int _heapchk( void );
```

## <a name="return-value"></a>Wartość zwracana

**_heapchk** zwraca jedną z następujących stałych manifestu liczb całkowitych zdefiniowanych w pliku malloc. h.

|Wartość zwracana|Warunek|
|-|-|
| **_HEAPBADBEGIN** | Informacje o początkowym nagłówku są nieprawidłowe lub nie można ich znaleźć. |
| **_HEAPBADNODE** | Znaleziono zły węzeł lub sterta jest uszkodzona. |
| **_HEAPBADPTR** | Wskaźnik do sterty jest nieprawidłowy. |
| **_HEAPEMPTY** | Sterta nie została zainicjowana. |
| **_HEAPOK** | Sterta wydaje się być spójna. |

Ponadto, jeśli wystąpi błąd, **_heapchk** ustawia **errno** na **ENOSYS**.

## <a name="remarks"></a>Uwagi

Funkcja **_heapchk** pomaga debugować problemy związane z stertą, sprawdzając, czy nie ma minimalnej spójności sterty. Jeśli system operacyjny nie obsługuje **_heapchk**(na przykład Windows 98), funkcja zwraca **_HEAPOK** i ustawia **errno** na **ENOSYS**.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|Opcjonalny nagłówek|
|-------------|---------------------|---------------------|
|**_heapchk**|\<malloc.h>|\<errno.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_heapchk.c
// This program checks the heap for
// consistency and prints an appropriate message.

#include <malloc.h>
#include <stdio.h>

int main( void )
{
   int  heapstatus;
   char *buffer;

   // Allocate and deallocate some memory
   if( (buffer = (char *)malloc( 100 )) != NULL )
      free( buffer );

   // Check heap status
   heapstatus = _heapchk();
   switch( heapstatus )
   {
   case _HEAPOK:
      printf(" OK - heap is fine\n" );
      break;
   case _HEAPEMPTY:
      printf(" OK - heap is empty\n" );
      break;
   case _HEAPBADBEGIN:
      printf( "ERROR - bad start of heap\n" );
      break;
   case _HEAPBADNODE:
      printf( "ERROR - bad node in heap\n" );
      break;
   }
}
```

```Output
OK - heap is fine
```

## <a name="see-also"></a>Zobacz także

[Alokacja pamięci](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
[_heapwalk](heapwalk.md)<br/>
