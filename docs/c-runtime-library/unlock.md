---
description: 'Dowiedz się więcej na temat: _unlock'
title: _unlock
ms.date: 11/04/2016
api_name:
- _unlock
api_location:
- msvcrt.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- unlock
- _unlock
helpviewer_keywords:
- unlock function
- _unlock function
ms.assetid: 2eda2507-a134-4997-aa12-f2f8cb319e14
ms.openlocfilehash: ca3b31dd2b1ff12f5dd98d93e12e76c3cc4f0864
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162158"
---
# <a name="_unlock"></a>_unlock

Zwalnia blokadę wielowątkowości.

> [!IMPORTANT]
> Ta funkcja jest przestarzała. Począwszy od programu Visual Studio 2015, nie jest on dostępny w CRT.

## <a name="syntax"></a>Składnia

```cpp
void __cdecl _unlock(
   int locknum
);
```

#### <a name="parameters"></a>Parametry

*locknum*<br/>
podczas Identyfikator blokady do wydania.

## <a name="requirements"></a>Wymagania

**Źródło:** MLOCK. c

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_lock](../c-runtime-library/lock.md)
