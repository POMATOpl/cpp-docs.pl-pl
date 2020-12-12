---
description: Dowiedz się więcej o strukturze RuntimeClassFlags
title: RuntimeClassFlags — Struktura
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
ms.openlocfilehash: 7874447fbbbe429884c5a79d0c70bb93e617ec61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209272"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags — Struktura

Zawiera typ wystąpienia elementu [RuntimeClass](runtimeclass-class.md).

## <a name="syntax"></a>Składnia

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>Parametry

*znaczników*<br/>
Wartość [wyliczenia RuntimeClassType —](runtimeclasstype-enumeration.md) .

## <a name="members"></a>Elementy członkowskie

### <a name="public-constants"></a>Stałe publiczne

|Nazwa|Opis|
|----------|-----------------|
|[RuntimeClassFlags::value, stała](#value-constant)|Zawiera wartość [wyliczenia RuntimeClassType —](runtimeclasstype-enumeration.md) .|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`RuntimeClassFlags`

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="runtimeclassflagsvalue-constant"></a><a name="value-constant"></a> RuntimeClassFlags:: value — stała

Pole, które zawiera wartość [wyliczenia RuntimeClassType —](runtimeclasstype-enumeration.md) .

```cpp
static const unsigned int value = flags;
```
