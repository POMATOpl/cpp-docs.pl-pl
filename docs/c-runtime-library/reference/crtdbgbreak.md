---
description: 'Dowiedz się więcej na temat: _CrtDbgBreak'
title: _CrtDbgBreak
ms.date: 11/04/2016
api_name:
- _CrtDbgBreak
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
- _CrtDbgBreak
- CrtDbgBreak
helpviewer_keywords:
- CrtDbgBreak function
- _CrtDbgBreak function
ms.assetid: 01f8b4a2-a2c7-4e1f-9f39-e573b4a7871f
ms.openlocfilehash: e92fa20e32ae02eab1b289878ad05826d8da0a85
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221569"
---
# <a name="_crtdbgbreak"></a>_CrtDbgBreak

Ustawia punkt przerwania w konkretnym wierszu kodu. (Używany tylko w trybie debugowania).

## <a name="syntax"></a>Składnia

```C
void _CrtDbgBreak( void );
```

## <a name="return-value"></a>Wartość zwracana

Brak zwracanej wartości.

## <a name="remarks"></a>Uwagi

Funkcja **_CrtDbgBreak** ustawia punkt przerwania debugowania w konkretnym wierszu kodu, w którym znajduje się funkcja. Ta funkcja jest używana tylko w trybie debugowania i jest zależna od wcześniej zdefiniowanych **_DEBUG** .

Aby uzyskać więcej informacji na temat korzystania z innych funkcji punktu w czasie wykonywania i pisania własnych zdefiniowanych przez klienta funkcji Hook, zobacz [pisanie własnych funkcji punktu zaczepienia debugowania](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_CrtDbgBreak**|\<CRTDBG.h>|

## <a name="libraries"></a>Biblioteki

Debuguj wersje wyłącznie [bibliotek uruchomieniowych C](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
[__debugbreak](../../intrinsics/debugbreak.md)<br/>
