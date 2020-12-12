---
description: 'Dowiedz się więcej na temat: feupdateenv'
title: feupdateenv
ms.date: 04/05/2018
api_name:
- feupdateenv
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
api_type:
- HeaderDef
f1_keywords:
- feupdateenv
- fenv/feupdateenv
helpviewer_keywords:
- feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
ms.openlocfilehash: 4e3fe47c6a03138f2bc82679eb5fc8e938678a17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289338"
---
# <a name="feupdateenv"></a>feupdateenv

Zapisuje aktualnie zgłoszone wyjątki zmiennoprzecinkowe, przywraca określony stan środowiska zmiennoprzecinkowego, a następnie podnosi zapisane wyjątki zmiennoprzecinkowe.

## <a name="syntax"></a>Składnia

```C
int feupdateenv(
   const fenv_t* penv
);
```

### <a name="parameters"></a>Parametry

*penv*<br/>
Wskaźnik do obiektu **fenv_t** , który zawiera środowisko zmiennoprzecinkowe określone przez wywołanie [fegetenv](fegetenv1.md) lub [feholdexcept](feholdexcept2.md). Można również określić domyślne Uruchamianie środowiska zmiennoprzecinkowego za pomocą makra FE_DFL_ENV.

## <a name="return-value"></a>Wartość zwracana

Zwraca wartość 0, jeśli wszystkie akcje zostały ukończone pomyślnie. W przeciwnym razie zwraca wartość różną od zera.

## <a name="remarks"></a>Uwagi

Funkcja **feupdateenv** wykonuje wiele akcji. Po pierwsze przechowuje flagi stanu wyjątków zmiennoprzecinkowych w automatycznym magazynie. Następnie ustawia bieżące środowisko zmiennoprzecinkowe z wartości przechowywanej w obiekcie **fenv_t** wskazywanym przez *PENV*. Jeśli *PENV* nie jest **FE_DFL_ENV** lub nie wskazuje prawidłowego obiektu **fenv_t** , kolejne zachowanie jest niezdefiniowane. Na koniec **feupdateenv** wywołuje lokalnie przechowywane wyjątki zmiennoprzecinkowe.

Aby użyć tej funkcji, należy wyłączyć optymalizacje zmiennoprzecinkowe, które mogą uniemożliwić dostęp przy użyciu `#pragma fenv_access(on)` dyrektywy przed wywołaniem. Aby uzyskać więcej informacji, zobacz [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Nagłówek języka C|Nagłówek C++|
|--------------|--------------|------------------|
|**feupdateenv**|\<fenv.h>|\<cfenv>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
