---
description: 'Dowiedz się więcej na temat: __pctype_func'
title: __pctype_func
ms.date: 4/2/2020
api_name:
- __pctype_func
- _o___pctype_func
api_location:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __pctype_func
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
ms.openlocfilehash: 80374d17015336e553c3ca566dd6752963dd3eef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213471"
---
# <a name="__pctype_func"></a>__pctype_func

Pobiera wskaźnik do tablicy informacji o klasyfikacji znaków.

## <a name="syntax"></a>Składnia

```cpp
const unsigned short *__pctype_func(
   )
```

## <a name="return-value"></a>Wartość zwracana

Wskaźnik do tablicy informacji o klasyfikacji znaków.

## <a name="remarks"></a>Uwagi

Informacje w tabeli klasyfikacji znaków są przeznaczone tylko do użytku wewnętrznego i są używane przez różne funkcje, które klasyfikują znaki typu **`char`** . Aby uzyskać więcej informacji, zobacz `Remarks` sekcję [_pctype, _pwctype, _wctype _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|__pctype_func|CType. h|

## <a name="see-also"></a>Zobacz też

[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
