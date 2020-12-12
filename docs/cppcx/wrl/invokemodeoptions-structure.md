---
description: Dowiedz się więcej o strukturze InvokeModeOptions
title: InvokeModeOptions, struktura
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 1e1382242c95c47355239c220c43c278280dd451
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298984"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions, struktura

Określa, czy mają być wyzwalane wszystkie zdarzenia w kolejce delegatów, czy też zatrzymać wywoływanie po wystąpieniu błędu. Wartości dozwolone są określone w `InvokeMode` wyliczeniu.

## <a name="syntax"></a>Składnia

```cpp
enum InvokeMode
{
   StopOnFirstError = 1,
   FireAll = 2,
};

struct InvokeModeOptions
{
   static const InvokeMode invokeMode = invokeModeValue;
};
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** Event. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL, przestrzeń nazw](microsoft-wrl-namespace.md)<br/>
[Microsoft:: WRL:: AgileEventSource, Klasa](agileeventsource-class.md)
