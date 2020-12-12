---
description: 'Dowiedz się więcej na temat: _lock'
title: _lock
ms.date: 11/04/2016
api_name:
- _lock
api_location:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- lock
- _lock
helpviewer_keywords:
- lock function
- _lock function
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
ms.openlocfilehash: 9b95c8b7ad0f0ce84348f9581d9acb611373a27b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331046"
---
# <a name="_lock"></a>_lock

Uzyskuje blokadę wielowątkowości.

> [!IMPORTANT]
> Ta funkcja jest przestarzała. Począwszy od programu Visual Studio 2015, nie jest on dostępny w CRT.

## <a name="syntax"></a>Składnia

```cpp
void __cdecl _lock
   int locknum
);
```

#### <a name="parameters"></a>Parametry

*locknum*<br/>
podczas Identyfikator blokady do pobrania.

## <a name="remarks"></a>Uwagi

Jeśli blokada została już pobrana, ta metoda uzyskuje blokadę i powoduje błąd wewnętrzny środowiska uruchomieniowego C (CRT). Jeśli metoda nie może uzyskać blokady, kończy się z powodu błędu krytycznego, a kod błędu zostanie ustawiony na `_RT_LOCK` .

## <a name="requirements"></a>Wymagania

**Źródło:** MLOCK. c

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_unlock](../c-runtime-library/unlock.md)
