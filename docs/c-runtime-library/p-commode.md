---
description: 'Dowiedz się więcej na temat: __p__commode'
title: __p__commode
ms.date: 4/2/2020
api_name:
- __p__commode
- _o___p__commode
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__commode
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
ms.openlocfilehash: f3f779196b650d05bb16c0da652d47946fc2a10d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213627"
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

`__p__commode`Funkcja jest tylko do użytku wewnętrznego i nie powinna być wywoływana z kodu użytkownika.

Tryb zatwierdzania plików określa, kiedy krytyczne dane są zapisywane na dysku. Aby uzyskać więcej informacji, zobacz [fflush](../c-runtime-library/reference/fflush.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|__p \_ _commode|wewnętrzny. h|
