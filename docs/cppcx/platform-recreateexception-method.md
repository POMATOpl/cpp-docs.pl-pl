---
description: 'Dowiedz się więcej na temat: platform:: recreateexception — Metoda'
title: 'Platform:: recreateexception — Metoda'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
ms.openlocfilehash: 273f60055e4cf5a940558ba5dcaa4aa6a7c70bca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308058"
---
# <a name="platformrecreateexception-method"></a>Platform:: recreateexception — Metoda

Ta metoda służy tylko do użytku wewnętrznego i nie jest przeznaczona do kodu użytkownika. Zamiast tego użyj metody Exception:: CreateException.

## <a name="syntax"></a>Składnia

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>Parametry

*godz.*

### <a name="property-valuereturn-value"></a>Wartość właściwości/Zwracana wartość

Zwraca nową platformę:: Exception ^, w oparciu o określoną wartość HRESULT.
