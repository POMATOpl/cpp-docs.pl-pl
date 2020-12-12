---
description: 'Dowiedz się więcej na temat: fesetexceptflag'
title: fesetexceptflag
ms.date: 04/05/2018
api_name:
- fesetexceptflag
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
- fesetexceptflag
- fenv/fesetexceptflag
helpviewer_keywords:
- fesetexceptflag function
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
ms.openlocfilehash: da37c4a032533ae35c8481413c27ca1cb2e8c3c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289416"
---
# <a name="fesetexceptflag"></a>fesetexceptflag

Ustawia określone flagi stanu zmiennoprzecinkowego w bieżącym środowisku zmiennoprzecinkowym.

## <a name="syntax"></a>Składnia

```C
int fesetexceptflag(
     const fexcept_t *pstatus,
     int excepts
);
```

### <a name="parameters"></a>Parametry

*pstatus*<br/>
Wskaźnik do obiektu **fexcept_t** zawierającego wartości, do których mają zostać ustawione flagi stanu wyjątku. Obiekt może być ustawiony przez poprzednie wywołanie do [fegetexceptflag](fegetexceptflag2.md).

*Oprócz*<br/>
Flagi stanu wyjątku zmiennoprzecinkowego do ustawienia.

## <a name="return-value"></a>Wartość zwracana

Jeśli wszystkie określone flagi stanu wyjątku zostały pomyślnie ustawione, zwraca wartość 0. W przeciwnym razie zwraca wartość różną od zera.

## <a name="remarks"></a>Uwagi

Funkcja **fesetexceptflag** ustawia stan wyjątków zmiennoprzecinkowych, określonych przez, *z wyjątkiem* odpowiednich wartości ustawionych w obiekcie **fexcept_t** wskazywanym przez *pstatus*.  Nie zgłasza wyjątków. Wskaźnik *pstatus* musi wskazywać prawidłowy obiekt **fexcept_t** lub kolejne zachowanie jest niezdefiniowane. Funkcja **fesetexceptflag** obsługuje te wartości makr wyjątków w *wyjątkiem*, zdefiniowanych w \<fenv.h> :

|Makro wyjątku|Opis|
|---------------------|-----------------|
|FE_DIVBYZERO|Wystąpił błąd Singularity lub wartość w poprzedniej operacji zmiennoprzecinkowej; utworzono nieskończoną wartość.|
|FE_INEXACT|Funkcja była zmuszona do zaokrąglania przechowywanego wyniku poprzedniej operacji zmiennoprzecinkowej.|
|FE_INVALID|Wystąpił błąd domeny w poprzedniej operacji zmiennoprzecinkowej.|
|FE_OVERFLOW|Wystąpił błąd zakresu; wcześniejszy wynik operacji zmiennoprzecinkowej był zbyt duży, aby można było go przedstawić.|
|FE_UNDERFLOW|Wcześniejszy wynik operacji zmiennoprzecinkowej był zbyt mały, aby mógł być reprezentowany z pełną dokładnością; utworzono nienormalną wartość.|
|FE_ALL_EXCEPT|Bitowe lub wszystkie obsługiwane wyjątki zmiennoprzecinkowe.|

Argument *except* może mieć wartość zero, jedno z obsługiwanych makr wyjątków zmiennoprzecinkowych lub bitowe lub dwa lub więcej makr. Wynik innej wartości argumentu jest niezdefiniowany.

Aby użyć tej funkcji, należy wyłączyć optymalizacje zmiennoprzecinkowe, które mogą uniemożliwić dostęp przy użyciu `#pragma fenv_access(on)` dyrektywy przed wywołaniem. Aby uzyskać więcej informacji, zobacz [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Nagłówek języka C|Nagłówek C++|
|--------------|--------------|------------------|
|**fesetexceptflag**|\<fenv.h>|\<cfenv>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[fegetexceptflag](fegetexceptflag2.md)<br/>
