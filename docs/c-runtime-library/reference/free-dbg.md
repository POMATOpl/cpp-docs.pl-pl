---
description: 'Dowiedz się więcej na temat: _free_dbg'
title: _free_dbg
ms.date: 11/04/2016
api_name:
- _free_dbg
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
- _free_dbg
- free_dbg
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
ms.openlocfilehash: 4baba591349c197b301b0dcd11b1998adfc7a971
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314038"
---
# <a name="_free_dbg"></a>_free_dbg

Zwalnia blok pamięci w stercie (tylko wersja do debugowania).

## <a name="syntax"></a>Składnia

```C
void _free_dbg(
   void *userData,
   int blockType
);
```

### <a name="parameters"></a>Parametry

*userData*<br/>
Wskaźnik do przydziału bloku pamięci, który ma zostać zwolniony.

*BlockType*<br/>
Typ przydzielony blok pamięci do zwolnienia: **_CLIENT_BLOCK**, **_NORMAL_BLOCK** lub **_IGNORE_BLOCK**.

## <a name="remarks"></a>Uwagi

Funkcja **_free_dbg** jest wersją debugowania [bezpłatnej](free.md) funkcji. Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, każde wywołanie **_free_dbg** zostanie zredukowane do wywołania **bezpłatnego**. Zarówno **bezpłatny** , jak i **_free_dbg** Zwolnij blok pamięci w stercie podstawowej, ale **_free_dbg** obsługuje dwie funkcje debugowania: możliwość przechowywania zwolnionych bloków na połączonej liście sterty w celu symulowania warunków niedostatecznej ilości pamięci i parametru typu bloku w celu zwolnienia określonych typów alokacji.

**_free_dbg** wykonuje sprawdzanie poprawności wszystkich określonych plików i lokalizacji blokowania przed wykonaniem operacji bezpłatnej. Aplikacja nie powinna podawać tych informacji. Gdy blok pamięci jest zwolniony, Menedżer sterty debugowania automatycznie sprawdza integralność buforów po obu stronach części użytkownika i wystawia raport o błędach, jeśli nastąpiło zastąpienie. Jeśli ustawiono **_CRTDBG_DELAY_FREE_MEM_DF** pole bitowe flagi [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) , zwolniony blok zostanie wypełniony wartością 0xDD, przypisanym typem bloku **_FREE_BLOCK** i przechowywanym na połączonej liście bloków pamięci sterty.

Jeśli wystąpi błąd podczas zwalniania pamięci, **errno** jest ustawiany z informacjami z systemu operacyjnego w przypadku awarii. Aby uzyskać więcej informacji, zobacz [errno, _doserrno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Aby uzyskać informacje o tym, jak bloki pamięci są przydzielane, inicjowane i zarządzane w wersji debugowania sterty podstawowej, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać informacje o typach bloków alokacji i sposobach ich użycia, zobacz [typy bloków na stercie debugowania](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać informacje o różnicach między wywołaniem standardowej funkcji sterty i jej wersji debugowania w kompilacji debugowania aplikacji, zobacz [debugowanie wersji funkcji alokacji sterty](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_free_dbg**|\<crtdbg.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

Przykład używania **_free_dbg** można znaleźć w temacie [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
