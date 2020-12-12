---
description: 'Dowiedz się więcej na temat: _findclose'
title: _findclose
ms.date: 4/2/2020
api_name:
- _findclose
- _o__findclose
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _findclose
- findclose
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
ms.openlocfilehash: 389a8aaf55605a1d9e3193c86ce500bf313fd631
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329200"
---
# <a name="_findclose"></a>_findclose

Zamyka określone dojście wyszukiwania i zwalnia skojarzone zasoby.

## <a name="syntax"></a>Składnia

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>Parametry

*uchwyty*<br/>
Dojście wyszukiwania zwrócone przez poprzednie wywołanie do **_findfirst**.

## <a name="return-value"></a>Wartość zwracana

Jeśli się powiedzie, **_findclose** zwraca wartość 0. W przeciwnym razie zwraca wartość-1 i ustawia **errno** na **ENOENT**, co oznacza, że nie można odnaleźć więcej pasujących plików.

## <a name="remarks"></a>Uwagi

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|
|--------------|---------------------|
|**_findclose**|\<io.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Wywołania systemowe](../../c-runtime-library/system-calls.md)<br/>
[Funkcje wyszukiwania nazw plików](../../c-runtime-library/filename-search-functions.md)<br/>
