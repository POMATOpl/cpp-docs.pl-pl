---
description: Dowiedz się więcej na temat klasy is_trivial
title: Klasa is_trivial
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivial
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
ms.openlocfilehash: 56e5a3c915893b88228f4a40307d2c1e3c32555d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247660"
---
# <a name="is_trivial-class"></a>Klasa is_trivial

Testuje, czy typ jest typem prostym.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *T* jest typem prostym, w przeciwnym razie ma wartość false. Typy uproszczone to typy skalarne, które można skopiować typy klas, tablice tych typów i wersje z kwalifikatorem CV tych typów.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
