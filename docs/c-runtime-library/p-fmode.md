---
description: 'Dowiedz się więcej na temat: __p__fmode'
title: __p__fmode
ms.date: 4/2/2020
api_name:
- __p__fmode
- _o___p__fmode
api_location:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __p__fmode
helpviewer_keywords:
- __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
ms.openlocfilehash: da7cae9c881ebe042aa5d6003b50c09c65ea02d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213523"
---
# <a name="__p__fmode"></a>__p__fmode

Wskazuje na `_fmode` zmienną globalną, która określa domyślny *tryb tłumaczenia plików* dla operacji we/wy pliku.

## <a name="syntax"></a>Składnia

```cpp
int* __p__fmode(
   );
```

## <a name="return-value"></a>Wartość zwracana

Wskaźnik na `_fmode` zmienną globalną.

## <a name="remarks"></a>Uwagi

`__p__fmode`Funkcja jest tylko do użytku wewnętrznego i nie powinna być wywoływana z kodu użytkownika.

Tryb tłumaczenia plików określa albo `binary` `text` tłumaczenie dla [_open](../c-runtime-library/reference/open-wopen.md) i [_pipe](../c-runtime-library/reference/pipe.md) operacji we/wy. Aby uzyskać więcej informacji, zobacz [_fmode](../c-runtime-library/fmode.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|__p \_ _fmode|STDLIB. h|
