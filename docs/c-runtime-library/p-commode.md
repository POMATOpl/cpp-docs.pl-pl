---
title: __p__commode | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __p__commode
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __p__commode
dev_langs:
- C++
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f610b26c79201f3431b6263a002b59df7456cfe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082446"
---
# <a name="pcommode"></a>__p__commode

Wskazuje `_commode` zmienna globalna, która określa domyślny *tryb zatwierdzania plików* dla operacji We/Wy pliku.

## <a name="syntax"></a>Składnia

```cpp
int * __p__commode(
   );
```

## <a name="return-value"></a>Wartość zwracana

Wskaźnik do `_commode` zmiennej globalnej.

## <a name="remarks"></a>Uwagi

`__p__commode` Funkcji jest tylko do użytku wewnętrznego i nie powinna być wywoływana z kodu użytkownika.

Tryb zatwierdzania pliku Określa, kiedy krytyczne dane są zapisywane na dysku. Aby uzyskać więcej informacji, zobacz [fflush —](../c-runtime-library/reference/fflush.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|__p\__commode|internal.h|