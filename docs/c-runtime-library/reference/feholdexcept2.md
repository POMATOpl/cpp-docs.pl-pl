---
description: 'Dowiedz się więcej na temat: feholdexcept'
title: feholdexcept
ms.date: 04/05/2018
api_name:
- feholdexcept
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- feholdexcept
- fenv/feholdexcept
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
ms.openlocfilehash: 89ccf9bedb05752202152f6bd862b11b2f765322
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322527"
---
# <a name="feholdexcept"></a>feholdexcept

Zapisuje bieżące środowisko zmiennoprzecinkowe w określonym obiekcie, czyści flagi stanu zmiennoprzecinkowego i, jeśli to możliwe, umieści środowisko zmiennoprzecinkowe w trybie niezatrzymania.

## <a name="syntax"></a>Składnia

```C
int feholdexcept(
   fenv_t *penv
);
```

### <a name="parameters"></a>Parametry

*penv*<br/>
Wskaźnik do obiektu **fenv_t** , aby zawierał kopię środowiska zmiennoprzecinkowego.

## <a name="return-value"></a>Wartość zwracana

Zwraca wartość zero, jeśli i tylko wtedy, gdy funkcja może pomyślnie włączyć zatrzymywanie obsługi wyjątków zmiennoprzecinkowych.

## <a name="remarks"></a>Uwagi

Funkcja **feholdexcept** służy do przechowywania stanu bieżącego środowiska zmiennoprzecinkowego w obiekcie **fenv_t** wskazywanym przez *PENV*, a w celu ustawienia środowiska nie przerywa wykonywania w wyjątkach zmiennoprzecinkowych. Jest to tzw. Tryb niezatrzymania.  Ten tryb jest kontynuowany do momentu przywrócenia środowiska przy użyciu [fesetenv](fesetenv1.md) lub [feupdateenv](feupdateenv.md).

Tej funkcji można użyć na początku procedury podrzędnej, która wymaga ukrycia co najmniej jednego wyjątku zmiennoprzecinkowego z obiektu wywołującego. Aby zgłosić wyjątek, można po prostu usunąć niepożądane wyjątki przy użyciu [feclearexcept,](feclearexcept1.md) a następnie zakończyć tryb niezatrzymania z wywołaniem do **feupdateenv**.

Aby użyć tej funkcji, należy wyłączyć optymalizacje zmiennoprzecinkowe, które mogą uniemożliwić dostęp przy użyciu `#pragma fenv_access(on)` dyrektywy przed wywołaniem. Aby uzyskać więcej informacji, zobacz [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Nagłówek języka C|Nagłówek C++|
|--------------|--------------|------------------|
|**feholdexcept**|\<fenv.h>|\<cfenv>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[fesetenv](fesetenv1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
