---
description: 'Dowiedz się więcej na temat: _CrtDoForAllClientObjects'
title: _CrtDoForAllClientObjects
ms.date: 11/04/2016
api_name:
- _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
ms.openlocfilehash: 73d2718aa4bfb68752a8424a385638a48aba2e36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319794"
---
# <a name="_crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

Wywołuje funkcję dostarczoną przez aplikację dla wszystkich typów **_CLIENT_BLOCK** w stercie (tylko wersja do debugowania).

## <a name="syntax"></a>Składnia

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>Parametry

*PFN*<br/>
Wskaźnik do funkcji wywołania zwrotnego funkcji dostarczonej przez aplikację. Pierwszy parametr tej funkcji wskazuje na dane. Drugi parametr jest wskaźnikiem kontekstu, który jest przesyłany do wywołania **_CrtDoForAllClientObjects**.

*Context*<br/>
Wskaźnik do kontekstu dostarczonego przez aplikację, który ma zostać przekazany do funkcji dostarczonej przez aplikację.

## <a name="remarks"></a>Uwagi

Funkcja **_CrtDoForAllClientObjects** przeszukuje połączoną listę sterty dla bloków pamięci z typem **_CLIENT_BLOCK** i wywołuje funkcję dostarczoną przez aplikację po znalezieniu bloku tego typu. Znaleziony blok i parametr *kontekstowy* są przekazane jako argumenty do funkcji dostarczonej przez aplikację. Podczas debugowania aplikacja może śledzić określoną grupę alokacji, jawnie wywołując funkcje sterty debugowania w celu przydzielenia pamięci i określając, że bloki mają przypisany **_CLIENT_BLOCK** typ bloku. Te bloki mogą być następnie śledzone oddzielnie i raportowane w różny sposób podczas wykrywania przecieków i raportowania stanu pamięci.

Jeśli **_CRTDBG_ALLOC_MEM_DF** polu bitowym flagi [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) nie jest włączona, **_CrtDoForAllClientObjects** natychmiast zwraca wartość. Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, wywołania do **_CrtDoForAllClientObjects** są usuwane podczas przetwarzania wstępnego.

Aby uzyskać więcej informacji o typie **_CLIENT_BLOCK** i sposobach ich użycia przez inne funkcje debugowania, zobacz [typy bloków na stercie debugowania](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać informacje o tym, jak bloki pamięci są przydzielane, inicjowane i zarządzane w wersji debugowania sterty podstawowej, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details).

Jeśli *PFN* ma **wartość null**, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, [errno, _doserrno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) jest ustawiona na **EINVAL** , a funkcja zwraca.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h>, \<errno.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

**Biblioteki:** Debuguj tylko wersje uniwersalnych bibliotek uruchomieniowych języka C.

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[Funkcje raportowania stanu sterty](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
