---
description: 'Dowiedz się więcej na temat: _CrtMemDumpAllObjectsSince'
title: _CrtMemDumpAllObjectsSince
ms.date: 11/04/2016
api_name:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
ms.openlocfilehash: e833543d3119b39a21b596af412a97f6991e4ef0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319641"
---
# <a name="_crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince

Zrzuca informacje o obiektach w stercie od rozpoczęcia wykonywania programu lub z określonego stanu sterty (tylko wersja do debugowania).

## <a name="syntax"></a>Składnia

```C
void _CrtMemDumpAllObjectsSince(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Parametry

*Państwu*<br/>
Wskaźnik do stanu sterty, aby rozpocząć zatopienie lub **wartość null**.

## <a name="remarks"></a>Uwagi

Funkcja **_CrtMemDumpAllObjectsSince** zrzuca informacje nagłówka debugowania obiektów przyznanych w stercie w formie możliwej do odczytu przez użytkownika. Informacje o zrzucie mogą być używane przez aplikację do śledzenia alokacji i wykrywania problemów z pamięcią. Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, wywołania do **_CrtMemDumpAllObjectsSince** są usuwane podczas przetwarzania wstępnego.

**_CrtMemDumpAllObjectsSince** używa wartości parametru *stanu* , aby określić, gdzie ma zostać zainicjowana operacja zrzutu. Aby rozpocząć zrzucanie od określonego stanu sterty, parametr *State* musi być wskaźnikiem do struktury **_CrtMemState** , która została wypełniona przez [_CrtMemCheckpoint](crtmemcheckpoint.md) przed wywołaniem **_CrtMemDumpAllObjectsSince** . Gdy *stan* ma **wartość null**, funkcja rozpoczyna zrzut od początku wykonywania programu.

Jeśli aplikacja zainstalowała funkcję haka zrzutu przez wywołanie [_CrtSetDumpClient](crtsetdumpclient.md), następnie za każdym razem, gdy **_CrtMemDumpAllObjectsSince** zrzutu informacji o **_CLIENT_BLOCK** typie bloku, wywoła również funkcję zrzutu dostarczoną przez aplikację. Domyślnie wewnętrzne bloki uruchomieniowe C (**_CRT_BLOCK**) nie są uwzględnione w operacjach zrzutu pamięci. Funkcja [_CrtSetDbgFlag](crtsetdbgflag.md) może służyć do włączania **_CRTDBG_CHECK_CRT_DF** bitowej **_crtDbgFlag** w celu uwzględnienia tych bloków. Ponadto bloki oznaczone jako zwolnione lub ignorowane (**_FREE_BLOCK**, **_IGNORE_BLOCK**) nie są uwzględniane w zrzucie pamięci.

Aby uzyskać więcej informacji o funkcjach stanu sterty i strukturze **_CrtMemState** , zobacz [funkcje raportowania stanu sterty](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać więcej informacji o tym, jak bloki pamięci są przydzielane, inicjowane i zarządzane w wersji debugowania sterty podstawowej, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_CrtMemDumpAll — ObjectsSince**|\<crtdbg.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Debuguj wersje wyłącznie [bibliotek uruchomieniowych C](../../c-runtime-library/crt-library-features.md) .

## <a name="example"></a>Przykład

Przykład używania **_CrtMemDumpAllObjectsSince** można znaleźć w temacie [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
