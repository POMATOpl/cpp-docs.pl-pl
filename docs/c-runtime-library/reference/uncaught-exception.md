---
title: __uncaught_exception | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __uncaught_exception
apilocation:
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
apitype: DLLExport
f1_keywords:
- __uncaught_exception
dev_langs:
- C++
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fcae75a5d25710866f781d766cfd77eceb977649
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408218"
---
# <a name="uncaughtexception"></a>__uncaught_exception

Wskazuje, czy co najmniej jeden wyjątek został zgłoszony, ale nie było obsługiwane przez odpowiednie **catch** zablokować z [try-catch](../../cpp/try-throw-and-catch-statements-cpp.md) instrukcji.

## <a name="syntax"></a>Składnia

```cpp
bool __uncaught_exception(
   );
```

## <a name="return-value"></a>Wartość zwracana

**wartość true,** od czasu jest zgłaszany wyjątek **spróbuj** bloku do dopasowywania **catch** blok jest zainicjowana; w przeciwnym razie **false**.

## <a name="remarks"></a>Uwagi

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|__uncaught_exception|EH.h|

## <a name="see-also"></a>Zobacz także

[Instrukcje try, throw i catch (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)<br/>
