---
description: 'Dowiedz się więcej na temat: __set_app_type'
title: __set_app_type
ms.date: 11/04/2016
api_name:
- __set_app_type
- _set_app_type
api_location:
- msvcr90.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __set_app_type
helpviewer_keywords:
- __set_app_type
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
ms.openlocfilehash: 19aafebc4f7fd848804e21193332fb693af56010
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246770"
---
# <a name="__set_app_type"></a>__set_app_type

Ustawia bieżący typ aplikacji.

## <a name="syntax"></a>Składnia

```cpp
void __set_app_type (
   int at
   )
```

#### <a name="parameters"></a>Parametry

*w*<br/>
Wartość wskazująca typ aplikacji. Możliwe wartości są następujące:

|Wartość|Opis|
|-----------|-----------------|
|_UNKNOWN_APP|Nieznany typ aplikacji.|
|_CONSOLE_APP|Aplikacja konsoli (wiersza polecenia).|
|_GUI_APP|Graficzny interfejs użytkownika (Windows).|

## <a name="remarks"></a>Uwagi

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|__set_app_type|wewnętrzny. h|
