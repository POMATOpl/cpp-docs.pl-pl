---
description: 'Dowiedz się więcej na temat: _CrtDumpMemoryLeaks'
title: _CrtDumpMemoryLeaks
ms.date: 11/04/2016
api_name:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
ms.openlocfilehash: 83b3effdc4f3e8afdad24057ab55123aee924d60
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319781"
---
# <a name="_crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks

Zrzuca wszystkie bloki pamięci w stercie debugowania, gdy wystąpi wyciek pamięci (tylko wersja Debug).

## <a name="syntax"></a>Składnia

```C

int _CrtDumpMemoryLeaks( void );
```

## <a name="return-value"></a>Wartość zwracana

**_CrtDumpMemoryLeaks** zwraca wartość true, jeśli znaleziono przeciek pamięci. W przeciwnym razie funkcja zwraca wartość FALSE.

## <a name="remarks"></a>Uwagi

Funkcja **_CrtDumpMemoryLeaks** określa, czy wyciek pamięci nastąpił od momentu rozpoczęcia wykonywania programu. Po znalezieniu przecieku informacje nagłówka debugowania dla wszystkich obiektów w stercie są zrzucane w formie możliwej do odczytu przez użytkownika. Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, wywołania do **_CrtDumpMemoryLeaks** są usuwane podczas przetwarzania wstępnego.

**_CrtDumpMemoryLeaks** jest często wywoływana po zakończeniu wykonywania programu, aby upewnić się, że wszystkie pamięci przydzielone przez aplikację zostały zwolnione. Funkcję można wywołać automatycznie przy zakończeniu działania programu, włączając pole **_CRTDBG_LEAK_CHECK_DF** bitowego flagi [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) przy użyciu funkcji [_CrtSetDbgFlag](crtsetdbgflag.md) .

**_CrtDumpMemoryLeaks** wywołań [_CrtMemCheckpoint](crtmemcheckpoint.md) , aby uzyskać bieżący stan sterty, a następnie skanuje stan dla bloków, które nie zostały zwolnione. Po napotkaniu niezwolnionego bloku **_CrtDumpMemoryLeaks** wywołuje [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) do zrzutu informacji dla wszystkich obiektów przyznanych w stercie od momentu rozpoczęcia wykonywania programu.

Domyślnie wewnętrzne bloki uruchomieniowe C (**_CRT_BLOCK**) nie są uwzględnione w operacjach zrzutu pamięci. Funkcja [_CrtSetDbgFlag](crtsetdbgflag.md) może służyć do włączania **_CRTDBG_CHECK_CRT_DF** bitowej **_crtDbgFlag** w celu uwzględnienia tych bloków w procesie wykrywania przecieków.

Aby uzyskać więcej informacji o funkcjach stanu sterty i strukturze **_CrtMemState** , zobacz [funkcje raportowania stanu sterty](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać więcej informacji o tym, jak bloki pamięci są przydzielane, inicjowane i zarządzane w wersji debugowania sterty podstawowej, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_CrtDumpMemoryLeaks**|\<crtdbg.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Debuguj wersje wyłącznie [bibliotek uruchomieniowych C](../../c-runtime-library/crt-library-features.md) .

## <a name="example"></a>Przykład

Przykład używania **_CrtDumpMemoryLeaks** można znaleźć w temacie [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
