---
description: Dowiedz się więcej na temat klasy is_trivially_destructible
title: Klasa is_trivially_destructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_destructible
helpviewer_keywords:
- is_trivially_destructible
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
ms.openlocfilehash: 41f36c027175cbf67049eed986b9188ba1532048
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154360"
---
# <a name="is_trivially_destructible-class"></a>Klasa is_trivially_destructible

Testuje, czy typ jest bardzo zniszczalnych.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_trivially_destructible;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest typem zniszczalnych i destruktor jest znany kompilatorowi, aby nie używał operacji innych niż uproszczone. W przeciwnym razie zawiera wartość false.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
