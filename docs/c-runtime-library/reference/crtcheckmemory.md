---
description: 'Dowiedz się więcej na temat: _CrtCheckMemory'
title: _CrtCheckMemory
ms.date: 11/04/2016
api_name:
- _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
ms.openlocfilehash: f2537997a9adc1c2346560d3b65eecc633933616
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221595"
---
# <a name="_crtcheckmemory"></a>_CrtCheckMemory

Potwierdza integralność bloków pamięci przydzieloną w stercie debugowania (tylko wersja do debugowania).

## <a name="syntax"></a>Składnia

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>Wartość zwracana

Jeśli się powiedzie, **_CrtCheckMemory** zwraca wartość true; w przeciwnym razie funkcja zwraca wartość FALSE.

## <a name="remarks"></a>Uwagi

Funkcja **_CrtCheckMemory** sprawdza poprawność pamięci przydzielonej przez menedżera sterty debugowania, weryfikując bazowe stertę podstawową i sprawdzając każdy blok pamięci. Jeśli wystąpi błąd lub niespójność pamięci w podstawowym stosie bazowym, informacje nagłówka debugowania lub bufory zastępowania, **_CrtCheckMemory** generuje raport debugowania zawierający informacje opisujące warunek błędu. Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, wywołania do **_CrtCheckMemory** są usuwane podczas przetwarzania wstępnego.

Zachowanie **_CrtCheckMemory** można kontrolować, ustawiając pola bitowe flagi [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) przy użyciu funkcji [_CrtSetDbgFlag](crtsetdbgflag.md) . Włączenie **_CRTDBG_CHECK_ALWAYS_DF** BITOWEGO pola na wyniki **_CrtCheckMemory** wywoływane za każdym razem, gdy zażądano operacji alokacji pamięci. Chociaż ta metoda spowalnia wykonywanie, jest przydatna do szybkiego przechwytywania błędów. Wyłączenie pola **_CRTDBG_ALLOC_MEM_DF** bitowego powoduje, że **_CrtCheckMemory** nie weryfikują sterty i od razu zwracają **wartość true**.

Ponieważ ta funkcja zwraca **wartość true** lub **false**, można ją przesłać do jednego z [_ASSERTych](assert-asserte-assert-expr-macros.md) makr, aby utworzyć prosty mechanizm obsługi błędów debugowania. Poniższy przykład powoduje niepowodzenie potwierdzenia w przypadku wykrycia uszkodzenia w stercie:

```C
_ASSERTE( _CrtCheckMemory( ) );
```

Aby uzyskać więcej informacji o tym, jak **_CrtCheckMemory** mogą być używane z innymi funkcjami debugowania, zobacz [funkcje raportowania stanu sterty](/visualstudio/debugger/crt-debug-heap-details). Aby zapoznać się z omówieniem zarządzania pamięcią i sterty debugowania, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Debuguj wersje wyłącznie [bibliotek uruchomieniowych C](../../c-runtime-library/crt-library-features.md) .

## <a name="example"></a>Przykład

Przykład używania **_CrtCheckMemory** można znaleźć w temacie [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
