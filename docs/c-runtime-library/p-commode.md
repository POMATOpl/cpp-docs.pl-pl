---
title: __p__commode
ms.date: 11/04/2016
api_name:
- __p__commode
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__commode
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
ms.openlocfilehash: 930eb45e8069bdd71b5a7986e229b229318d0be8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944118"
---
# <a name="__p__commode"></a>__p__commode

Wskazuje na `_commode` zmienną globalną, która określa domyślny *tryb zatwierdzania plików* dla operacji we/wy pliku.

## <a name="syntax"></a>Składnia

```cpp
int * __p__commode(
   );
```

## <a name="return-value"></a>Wartość zwracana

Wskaźnik na `_commode` zmienną globalną.

## <a name="remarks"></a>Uwagi

`__p__commode` Funkcja jest tylko do użytku wewnętrznego i nie powinna być wywoływana z kodu użytkownika.

Tryb zatwierdzania plików określa, kiedy krytyczne dane są zapisywane na dysku. Aby uzyskać więcej informacji, zobacz [fflush](../c-runtime-library/reference/fflush.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|__p\__commode|internal.h|