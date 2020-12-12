---
description: 'Dowiedz się więcej na temat: __getmainargs, __wgetmainargs'
title: __getmainargs, __wgetmainargs
ms.date: 11/04/2016
api_name:
- __wgetmainargs
- __getmainargs
api_location:
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __wgetmainargs
- __getmainargs
helpviewer_keywords:
- __wgetmainargs
- __getmainargs
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
ms.openlocfilehash: 6f06f83a72d037df6a0973b24ac92ecade6c21eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181751"
---
# <a name="__getmainargs-__wgetmainargs"></a>__getmainargs, __wgetmainargs

Wywołuje analizę wiersza polecenia i kopiuje argumenty do `main()` tyłu przez przekazane wskaźniki.

## <a name="syntax"></a>Składnia

```cpp
int __getmainargs(
    int * _Argc,
   char *** _Argv,
   char **_ _Env,
   int _DoWildCard,
_startupinfo _ _StartInfo);

int __wgetmainargs (
   int *_Argc,
   wchar_t ***_Argv,
   wchar_t **__Env,
   int _DoWildCard,
   _startupinfo _ _StartInfo)
```

#### <a name="parameters"></a>Parametry

`_Argc`<br/>
Liczba całkowita, która zawiera liczbę argumentów po elemencie `argv` . Parametr `argc` jest zawsze większy lub równy 1.

`_Argv`<br/>
Tablica ciągów zakończonych znakiem null, która reprezentuje argumenty wiersza polecenia wprowadzone przez użytkownika programu. Zgodnie z Konwencją, `argv[0]` jest poleceniem, z którym wywoływany jest program, argv [1] jest pierwszym argumentem wiersza polecenia i tak dalej, do argv [argc], który jest zawsze **wartością null**. Pierwszy argument wiersza polecenia jest zawsze `argv[1]` i ostatnim z nich jest `argv[argc - 1]` .

`_Env`<br/>
Tablica ciągów, które reprezentują zmienne ustawione w środowisku użytkownika. Ta tablica została zakończona przez wpis o **wartości null** .

`_DoWildCard`<br/>
Liczba całkowita, która po ustawieniu na 1 rozszerza symbole wieloznaczne w argumentach wiersza polecenia lub jeśli wartość 0 nic nie robi.

`_StartInfo`<br/>
Inne informacje do przesłania do biblioteki CRT DLL.

## <a name="return-value"></a>Wartość zwracana

0, jeśli pomyślne; wartość ujemna, jeśli nie powiedzie się.

## <a name="remarks"></a>Uwagi

Używaj `__getmainargs` na platformach nieszerokich znaków oraz `__wgetmainargs` na platformach szerokich znaków (Unicode).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|__getmainargs|wewnętrzny. h|
|__wgetmainargs|wewnętrzny. h|
