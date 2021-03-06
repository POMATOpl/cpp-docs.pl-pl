---
description: 'Dowiedz się więcej o: fegetround, fesetround'
title: fegetround, fesetround
ms.date: 04/05/2018
api_name:
- fegetround
- fesetround
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
- fegetround
- fesetround
- fenv/fegetround
- fenv/fesetround
helpviewer_keywords:
- fegetround function
- fesetround function
ms.assetid: 596af00b-be2f-4f57-b2f5-460485f9ff0b
ms.openlocfilehash: f3c112efc1c380ac4ce4495f4365e2a47a1d8fd2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322553"
---
# <a name="fegetround-fesetround"></a>fegetround, fesetround

Pobiera lub ustawia bieżący tryb zaokrąglania zmiennoprzecinkowego.

## <a name="syntax"></a>Składnia

```C
int fegetround(void);

int fesetround(
   int round_mode
);
```

### <a name="parameters"></a>Parametry

*round_mode*<br/>
Tryb zaokrąglania, który ma zostać ustawiony, jako jedno z makr zaokrągleń zmiennoprzecinkowego. Jeśli wartość nie jest równa jednemu z makr zaokrągleń zmiennoprzecinkowego, tryb zaokrąglania nie jest zmieniany.

## <a name="return-value"></a>Wartość zwracana

Po powodzeniu funkcja **fegetround** zwraca tryb zaokrąglania jako jedną z wartości makr liczbowych zmiennoprzecinkowych. Zwraca wartość ujemną, jeśli nie można określić bieżącego trybu zaokrąglania.

Po powodzeniu funkcja **fesetround** zwraca wartość 0. W przeciwnym razie zwracana jest wartość różna od zera.

## <a name="remarks"></a>Uwagi

Operacje zmiennoprzecinkowe mogą korzystać z jednego z kilku trybów zaokrąglania. Te kontrolki wskazujące kierunek wykonywania operacji zmiennoprzecinkowych są zaokrąglane do momentu, w którym są przechowywane wyniki. Są to nazwy i zachowania w przypadku makr zaokrągleń zmiennoprzecinkowego zdefiniowanych w \<fenv.h> :

|Makro|Opis|
|-----------|-----------------|
|FE_DOWNWARD|Zaokrąglij do ujemnej nieskończoności.|
|FE_TONEAREST|Zaokrąglij do najbliższej.|
|FE_TOWARDZERO|Zaokrąglij do zera.|
|FE_UPWARD|Zaokrąglij do nieskończoności dodatniej.|

Domyślnym zachowaniem FE_TONEAREST jest zaokrąglenie wyników w połowie wartości w przybliżeniu do najbliższej wartości z parzystą (0) najmniej znaczącym bitem.

Bieżący tryb zaokrąglania ma wpływ na te operacje:

- Konwersje ciągów.

- Wyniki operatorów arytmetycznych zmiennoprzecinkowych spoza wyrażeń stałych.

- Funkcje zaokrąglania biblioteki, takie jak **rukuj** i **nearbyint —**.

- Zwraca wartości z funkcji matematycznych biblioteki standardowej.

Bieżący tryb zaokrąglania nie ma wpływu na te operacje:

- Funkcje biblioteki **TRUNC —**, **ceil —**, **Floor** i **lround** .

- Wartości zmiennoprzecinkowe do niejawnych rzutowania i konwersji, które zawsze są zaokrąglane w kierunku zera.

- Wyniki operatorów arytmetycznych zmiennoprzecinkowych w wyrażeniach stałych, które zawsze są zaokrąglane do najbliższej wartości.

Aby korzystać z tych funkcji, należy wyłączyć optymalizacje zmiennoprzecinkowe, które mogą uniemożliwić dostęp przy użyciu `#pragma fenv_access(on)` dyrektywy przed wywołaniem. Aby uzyskać więcej informacji, zobacz [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Nagłówek języka C|Nagłówek C++|
|--------------|--------------|------------------|
|**fegetround**, **fesetround**|\<fenv.h>|\<cfenv>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[nearbyint, nearbyintf, nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[rint, rintf, rintl](rint-rintf-rintl.md)<br/>
[lrint, lrintf, lrintl, llrint, llrintf, llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
