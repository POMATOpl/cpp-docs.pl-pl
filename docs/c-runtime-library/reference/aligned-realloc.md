---
description: 'Dowiedz się więcej na temat: _aligned_realloc'
title: _aligned_realloc
ms.date: 4/2/2020
api_name:
- _aligned_realloc
- _o__aligned_realloc
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
- _aligned_realloc
- aligned_realloc
helpviewer_keywords:
- aligned_realloc function
- _aligned_realloc function
ms.assetid: 80ce96e8-6087-416f-88aa-4dbb8cb1d218
ms.openlocfilehash: 305610f7eed8be180c9324f0e1e56e4af2f6a79b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312491"
---
# <a name="_aligned_realloc"></a>_aligned_realloc

Zmienia rozmiar bloku pamięci, który został przydzielony do [_aligned_malloc](aligned-malloc.md) lub [_aligned_offset_malloc](aligned-offset-malloc.md).

## <a name="syntax"></a>Składnia

```C
void * _aligned_realloc(
   void *memblock,
   size_t size,
   size_t alignment
);
```

### <a name="parameters"></a>Parametry

*memblock*<br/>
Bieżący wskaźnik bloku pamięci.

*zmienia*<br/>
Rozmiar alokacji żądanej pamięci.

*struktury*<br/>
Wartość wyrównania, która musi być całkowitą potęgą liczby 2.

## <a name="return-value"></a>Wartość zwracana

**_aligned_realloc** zwraca wskaźnik void do ponownie przydzielony blok pamięci (i prawdopodobnie przeniesiony). Wartość zwracana ma wartość **null** , jeśli rozmiar ma wartość zero, a argument buforu nie ma **wartości null** lub jeśli nie ma wystarczającej ilości dostępnej pamięci, aby rozszerzyć blok na dany rozmiar. W pierwszym przypadku, oryginalny blok jest zwolniony. W drugim bloku oryginalny nie jest zmieniany. Wartość zwracana wskazuje miejsce do magazynowania, które jest gwarantowane odpowiednio wyrównane do przechowywania dowolnego typu obiektu. Aby uzyskać wskaźnik do typu innego niż void, należy użyć rzutowania typu dla zwracanej wartości.

Wystąpił błąd podczas ponownego przydzielenia pamięci i zmiany wyrównania bloku.

## <a name="remarks"></a>Uwagi

**_aligned_realloc** jest oparty na **malloc**. Aby uzyskać więcej informacji o korzystaniu z **_aligned_offset_malloc**, zobacz [malloc](malloc.md).

Ta funkcja ustawia **errno** na **ENOMEM** , jeśli alokacja pamięci nie powiodła się lub żądany rozmiar był większy niż **_HEAP_MAXREQ**. Aby uzyskać więcej informacji na temat **errno**, zobacz [errno, _doserrno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ponadto **_aligned_realloc** sprawdza poprawność jego parametrów. Jeśli *wyrównanie* nie jest potęgą liczby 2, ta funkcja wywołuje procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, ta funkcja zwraca **wartość null** i ustawia **errno** na **EINVAL**.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_aligned_realloc**|\<malloc.h>|

## <a name="example"></a>Przykład

Aby uzyskać więcej informacji, zobacz [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Zobacz też

[Wyrównanie danych](../../c-runtime-library/data-alignment.md)<br/>
