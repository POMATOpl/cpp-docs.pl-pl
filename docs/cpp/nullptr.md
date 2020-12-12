---
description: 'Dowiedz się więcej na temat: nullptr'
title: nullptr
ms.date: 07/22/2020
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 8d7eb3a578addc14b85c53c50ab81c6e5592d541
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146155"
---
# <a name="nullptr"></a>nullptr

**`nullptr`** Słowo kluczowe Określa stałą wskaźnika typu o wartości null `std::nullptr_t` , która jest możliwa do przekonwertowania na dowolny nieprzetworzony typ wskaźnika.  Chociaż możesz użyć słowa kluczowego **`nullptr`** bez dołączania żadnych nagłówków, jeśli kod używa tego typu `std::nullptr_t` , należy go zdefiniować, dołączając nagłówek `<cstddef>` .

> [!NOTE]
> **`nullptr`** Słowo kluczowe jest również zdefiniowane w języku C++/CLI dla aplikacji kodu zarządzanego i nie jest zamienne ze standardem słowa kluczowego ISO języka c++. Jeśli kod można skompilować przy użyciu [`/clr`](../build/reference/clr-common-language-runtime-compilation.md) opcji kompilatora, która jest celem kodu zarządzanego, a następnie użyć `__nullptr` w dowolnym wierszu kodu, w którym należy zagwarantować, że kompilator używa natywnej interpretacji języka C++. Aby uzyskać więcej informacji, zobacz [ `nullptr` (c++/CLI i c++/CX)](../extensions/nullptr-cpp-component-extensions.md).

## <a name="remarks"></a>Uwagi

Unikaj używania `NULL` lub zera ( `0` ) jako stałej wskaźnika o wartości null; **`nullptr`** jest mniej podatne na niewłaściwe użycie i działa lepiej w większości sytuacji.  Na przykład, w przypadku `func(std::pair<const char *, double>)` wywołania `func(std::make_pair(NULL, 3.14))` powoduje błąd kompilatora.  Makro `NULL` powiększa się do `0` , tak aby wywołanie `std::make_pair(0, 3.14)` zwracało `std::pair<int, double>` , które nie jest konwertowane na `std::pair<const char *, double>` Typ parametru w `func` .  Wywołanie `func(std::make_pair(nullptr, 3.14))` zostało pomyślnie skompilowane `std::make_pair(nullptr, 3.14)` , ponieważ zwraca `std::pair<std::nullptr_t, double>` , który jest konwertowany na `std::pair<const char *, double>` .

## <a name="see-also"></a>Zobacz też

[Słowa kluczowe](../cpp/keywords-cpp.md)<br/>
[`nullptr` (C++/CLI i C++/CX)](../extensions/nullptr-cpp-component-extensions.md)
