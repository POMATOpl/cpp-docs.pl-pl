---
description: Dowiedz się więcej na temat klasy messages_base
title: messages_base — Klasa
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_base
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
ms.openlocfilehash: 45ea81b02bd15011c9f98b9364ea9918e248692a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230591"
---
# <a name="messages_base-class"></a>messages_base — Klasa

Klasa bazowa opisuje **`int`** Typ wykazu komunikatów.

## <a name="syntax"></a>Składnia

```cpp
struct messages_base : locale::facet {
    typedef int catalog;
    explicit messages_base(size_t _Refs = 0)
};
```

## <a name="remarks"></a>Uwagi

Wykaz typów jest synonimem typu **`int`** , który opisuje możliwe wartości zwracane z komunikatów:: [do_open](../standard-library/messages-class.md#do_open).

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<locale>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
