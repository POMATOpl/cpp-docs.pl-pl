---
title: Metoda platform::RecreateException
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
ms.openlocfilehash: 8173377a3d7a75bc85088037c229bac19f341649
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568873"
---
# <a name="platformrecreateexception-method"></a>Metoda platform::ReCreateException

Ta metoda jest tylko do użytku wewnętrznego i nie jest przeznaczony dla kodu użytkownika. Zamiast tego użyj metody Exception::CreateException.

## <a name="syntax"></a>Składnia

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>Parametry

*godz.*

### <a name="property-valuereturn-value"></a>Wartość właściwości/Zwracana wartość

Zwraca nowy Platform::Exception ^ zgodnie z określonym HRESULT.
