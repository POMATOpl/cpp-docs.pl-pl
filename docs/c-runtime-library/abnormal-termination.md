---
description: 'Dowiedz się więcej na temat: _abnormal_termination'
title: _abnormal_termination
ms.date: 11/04/2016
api_name:
- _abnormal_termination
api_location:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _abnormal_termination
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
ms.openlocfilehash: 2fa4b82deeebda7624d8ac96be675efc100ae926
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224286"
---
# <a name="_abnormal_termination"></a>_abnormal_termination

Wskazuje, czy **`__finally`** blok [instrukcji try-finally](../cpp/try-finally-statement.md) jest wprowadzany, gdy system wykonuje wewnętrzną listę programów obsługi zakończenia.

## <a name="syntax"></a>Składnia

```cpp
int   _abnormal_termination(
   );
```

## <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli system *rozwinięcia* stosu; w przeciwnym razie **`false`** .

## <a name="remarks"></a>Uwagi

Jest to wewnętrzna funkcja używana do zarządzania wyjątkami, która nie jest przeznaczona do wywoływania z kodu użytkownika.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|_abnormal_termination|EXCPT. h|

## <a name="see-also"></a>Zobacz też

[try-finally — instrukcja](../cpp/try-finally-statement.md)
