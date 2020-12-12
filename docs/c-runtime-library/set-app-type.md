---
description: 'Dowiedz się więcej na temat: _set_app_type'
title: _set_app_type
ms.date: 4/2/2020
api_name:
- _set_app_type
- _o__set_app_type
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
ms.openlocfilehash: cd04f1c17f7876c08f8eafb4ef77960073fb3f33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277105"
---
# <a name="_set_app_type"></a>_set_app_type

Funkcja wewnętrzna używana podczas uruchamiania, aby określić, czy aplikacja jest aplikacją konsolową, czy z graficznym interfejsem użytkownika.

## <a name="syntax"></a>Składnia

```cpp
typedef enum _crt_app_type
{
    _crt_unknown_app,
    _crt_console_app,
    _crt_gui_app
} _crt_app_type;

void __cdecl _set_app_type(
    _crt_app_type appType
    );
```

## <a name="parameters"></a>Parametry

*Typ aplikacji*<br/>
Wartość wskazująca typ aplikacji. Możliwe wartości są następujące:

|Wartość|Opis|
|----------------|-----------------|
|_crt_unknown_app|Nieznany typ aplikacji.|
|_crt_console_app|Aplikacja konsoli (wiersza polecenia).|
|_crt_gui_app|Graficzny interfejs użytkownika (Windows).|

## <a name="remarks"></a>Uwagi

Zwykle nie trzeba wywoływać tej funkcji. Jest częścią kodu uruchomienia środowiska uruchomieniowego języka C, który `main` jest wykonywany przed wywołaniem w aplikacji.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|_set_app_type|Process. h|
