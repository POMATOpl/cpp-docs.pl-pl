---
description: Dowiedz się więcej na temat klasy is_trivially_copyable
title: Klasa is_trivially_copyable
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copyable
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
ms.openlocfilehash: 0c3590f1549f064492b361ae2ddeff665e9365ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118475"
---
# <a name="is_trivially_copyable-class"></a>Klasa is_trivially_copyable

Testuje, czy typ jest typu, który jest jednocześnie kopiowany.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest typu, który jest jednocześnie kopiowany, w przeciwnym razie ma wartość false. Typy, które można kopiować, nie mają nieuproszczonych operacji kopiowania, operacji przenoszenia lub destruktorów. Ogólnie rzecz biorąc, operacja kopiowania jest traktowana jako uproszczona, jeśli może być zaimplementowana jako kopia bitowa. Zarówno typy wbudowane, jak i tablice typów, które mogą być kopiujące, są proste do skopiowania.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
