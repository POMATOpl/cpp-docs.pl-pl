---
title: _getmbcp
ms.date: 11/04/2016
apiname:
- _getmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getmbcp
- getmbcp
helpviewer_keywords:
- code pages, determining current
- _getmbcp function
- getmbcp function
ms.assetid: 2db202d4-5c3d-4871-a0b8-ceb0b79ee7bb
ms.openlocfilehash: 4cea84fc771a1d847814d002294391256efae57b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620457"
---
# <a name="getmbcp"></a>_getmbcp

Pobiera bieżącej stronie kodowej.

## <a name="syntax"></a>Składnia

```C
int _getmbcp( void );
```

## <a name="return-value"></a>Wartość zwracana

Zwraca bieżącej strony kodowe wielobajtowe. Zwracana wartość wynosząca 0 wskazuje, że strona kodowa pojedynczych bajtów jest używany.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_getmbcp**|\<mbctype.h>|

Aby uzyskać więcej informacji na temat zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz także

[_setmbcp](setmbcp.md)<br/>
