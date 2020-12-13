---
description: 'Dowiedz się więcej na temat: _getmbcp'
title: _getmbcp
ms.date: 4/2/2020
api_name:
- _getmbcp
- _o__getmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getmbcp
- getmbcp
helpviewer_keywords:
- code pages, determining current
- _getmbcp function
- getmbcp function
ms.assetid: 2db202d4-5c3d-4871-a0b8-ceb0b79ee7bb
ms.openlocfilehash: a4b249d4cee94e5dc0755e72158aed2ffcee7efb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332866"
---
# <a name="_getmbcp"></a>_getmbcp

Pobiera bieżącą stronę kodową.

## <a name="syntax"></a>Składnia

```C
int _getmbcp( void );
```

## <a name="return-value"></a>Wartość zwracana

Zwraca bieżącą stronę kodową wielobajtowego. Zwracana wartość 0 wskazuje, że jest używana strona kodowa jednobajtowego.

## <a name="remarks"></a>Uwagi

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_getmbcp**|\<mbctype.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[_setmbcp](setmbcp.md)<br/>
