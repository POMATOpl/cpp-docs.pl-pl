---
description: 'Dowiedz się więcej na temat: fesetenv'
title: fesetenv
ms.date: 04/05/2018
api_name:
- fesetenv
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
- fesetenv
- fenv/fesetenv
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
ms.openlocfilehash: 662634e467eb224af813f60ab4434d4857d21d50
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289442"
---
# <a name="fesetenv"></a>fesetenv

Ustawia bieżące środowisko zmiennoprzecinkowe.

## <a name="syntax"></a>Składnia

```C
int fesetenv(
   const fenv_t *penv
);
```

### <a name="parameters"></a>Parametry

*penv*<br/>
Wskaźnik do obiektu **fenv_t** , który zawiera środowisko zmiennoprzecinkowe określone przez wywołanie [fegetenv](fegetenv1.md) lub [feholdexcept](feholdexcept2.md). Można również określić domyślne Uruchamianie środowiska zmiennoprzecinkowego za pomocą makra **FE_DFL_ENV** .

## <a name="return-value"></a>Wartość zwracana

Zwraca wartość 0, jeśli środowisko zostało pomyślnie ustawione. W przeciwnym razie zwraca wartość różną od zera.

## <a name="remarks"></a>Uwagi

Funkcja **fesetenv** ustawia bieżące środowisko zmiennoprzecinkowe z wartości przechowywanej w obiekcie **fenv_t** wskazywanym przez *PENV*. Środowisko zmiennoprzecinkowe jest zestawem flag stanu i trybów kontroli, które wpływają na obliczenia zmiennoprzecinkowe. Obejmuje to tryb zaokrąglania oraz flagi stanu dla wyjątków zmiennoprzecinkowych.  Jeśli *PENV* nie jest **FE_DFL_ENV** lub nie wskazuje prawidłowego obiektu **fenv_t** , kolejne zachowanie jest niezdefiniowane.

Wywołanie tej funkcji ustawia flagi stanu wyjątku, które znajdują się w obiekcie *PENV* , ale nie zgłasza tych wyjątków.

Aby użyć tej funkcji, należy wyłączyć optymalizacje zmiennoprzecinkowe, które mogą uniemożliwić dostęp przy użyciu `#pragma fenv_access(on)` dyrektywy przed wywołaniem. Aby uzyskać więcej informacji, zobacz [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Nagłówek języka C|Nagłówek C++|
|--------------|--------------|------------------|
|**fesetenv**|\<fenv.h>|\<cfenv>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
