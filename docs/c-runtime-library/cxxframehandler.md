---
description: 'Dowiedz się więcej na temat: __CxxFrameHandler'
title: __CxxFrameHandler
ms.date: 11/04/2016
api_name:
- __CxxFrameHandler
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __CxxFrameHandler
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
ms.openlocfilehash: 3ebd4cefb303661b4b0293f3b4b3d42a915ddd56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326366"
---
# <a name="__cxxframehandler"></a>__CxxFrameHandler

Wewnętrzna funkcja CRT. Używane przez CRT do obsługi ramek wyjątków strukturalnych.

## <a name="syntax"></a>Składnia

```cpp
EXCEPTION_DISPOSITION __CxxFrameHandler(
      EHExceptionRecord  *pExcept,
      EHRegistrationNode *pRN,
      void               *pContext,
      DispatcherContext  *pDC
   )
```

#### <a name="parameters"></a>Parametry

*pExcept*<br/>
Rekord wyjątku, który jest przesyłany do możliwych **`catch`** instrukcji.

*pRN*<br/>
Informacje dynamiczne dotyczące ramki stosu, która jest używana do obsługi wyjątku. Aby uzyskać więcej informacji, zobacz ehdata. h.

*pContext*<br/>
Context. (Nieużywane na procesorach Intel).

*Domeny*<br/>
Dodatkowe informacje na temat wpisu funkcji i ramki stosu.

## <a name="return-value"></a>Wartość zwracana

Jedno z wartości *wyrażenia filtru* używane przez [instrukcję try-except](../cpp/try-except-statement.md).

## <a name="remarks"></a>Uwagi

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|__CxxFrameHandler|EXCPT. h, ehdata. h|
