---
description: Dowiedz się więcej na temat klasy underlying_type
title: Klasa underlying_type
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::underlying_type
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
ms.openlocfilehash: e717abe854f13fc96926deba1d4bf177529618cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132707"
---
# <a name="underlying_type-class"></a>Klasa underlying_type

Tworzy podstawowy typ całkowity dla typu wyliczenia.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do modyfikacji.

## <a name="remarks"></a>Uwagi

Element `type` typedef elementu członkowskiego szablonu klasy nazywa podstawowy typ całkowity *t*, gdy *t* jest typem wyliczenia, w przeciwnym razie nie ma składowej typedef `type` .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
