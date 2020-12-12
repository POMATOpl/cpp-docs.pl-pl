---
description: 'Dowiedz się więcej na temat: pointers_to_members pragma'
title: pointers_to_members, pragma
ms.date: 08/29/2019
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
helpviewer_keywords:
- class members, pointers to
- pragmas, pointers_to_members
- members, pointers to
- pointers_to_members pragma
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
ms.openlocfilehash: 5e1b66ce39f49889a1225facd4bf358231863063
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325722"
---
# <a name="pointers_to_members-pragma"></a>pointers_to_members, pragma

**Specyficzne dla języka C++**

Określa, czy wskaźnik do składowej klasy może być zadeklarowany przed jego definicją klasy skojarzonej. Służy do kontrolowania rozmiaru wskaźnika i kodu wymaganego do interpretacji wskaźnika.

## <a name="syntax"></a>Składnia

> **#pragma pointers_to_members (** *wskaźnik — deklaracja* [ **,** *najbardziej ogólna — reprezentacja* ])

## <a name="remarks"></a>Uwagi

Można umieścić **pointers_to_members** pragmę w pliku źródłowym jako alternatywę przy użyciu opcji kompilatora [/VMB lub/VMG](../build/reference/vmb-vmg-representation-method.md) lub [słów kluczowych dziedziczenia](../cpp/inheritance-keywords.md).

Argument *deklaracji wskaźnika* określa, czy zadeklarowano wskaźnik do składowej przed lub po definicji powiązanej funkcji. Argument *deklaracji wskaźnika* jest jednym z dwóch następujących symboli:

| Argument | Komentarze |
|--------------|--------------|
| **full_generality** | Generuje bezpieczny, czasem nieoptymalny kod. Użyj **full_generality** , jeśli dowolny wskaźnik do składowej jest zadeklarowany przed definicją klasy skojarzonej. Ten argument zawsze używa reprezentacji wskaźnika określonej przez argument z *największą ogólną reprezentacją* . Równoważny z /vmg. |
| **best_case** | Generuje bezpieczny, optymalny kod przy użyciu reprezentacji najlepszego przypadku dla wszystkich wskaźników do członków. Wymaga zdefiniowania klasy przed zadeklarowaniem wskaźnika do składowej klasy. Wartość domyślna to **best_case**. |

Argument *najbardziej ogólna reprezentacja* określa najmniejszą reprezentację wskaźnika, którą kompilator może bezpiecznie użyć, aby odwołać się do dowolnego wskaźnika do składowej klasy w jednostce translacji. Argument może być jedną z następujących wartości:

| Argument | Komentarze |
|--------------|--------------|
| **single_inheritance** | Najbardziej ogólną reprezentacją jest pojedyncze dziedziczenie, wskaźnik do funkcji członkowskiej. Powoduje błąd, jeśli model dziedziczenia definicji klasy, do której zgłaszany jest wskaźnik do składowej, jest wielokrotny lub wirtualny. |
| **multiple_inheritance** | Najbardziej ogólną reprezentacją jest wielokrotne dziedziczenie, wskaźnik do funkcji członkowskiej. Powoduje błąd, jeśli model dziedziczenia definicji klasy, do której zgłaszany jest wskaźnik do składowej, jest wirtualny. |
| **virtual_inheritance** | Najbardziej ogólną reprezentacją jest wirtualne dziedziczenie, wskaźnik do funkcji członkowskiej. Nigdy nie powoduje błędu. **virtual_inheritance** jest domyślnym argumentem, gdy `#pragma pointers_to_members(full_generality)` jest używany. |

> [!CAUTION]
> Firma Microsoft zaleca umieszczenie dyrektywy pragma **pointers_to_members** tylko w pliku kodu źródłowego, który ma mieć wpływ, i tylko po dodaniu `#include` dyrektyw. Ta metoda zmniejsza ryzyko, że pragma wpłynie na inne pliki i przypadkowo określi wiele definicji dla tej samej zmiennej, funkcji lub nazwy klasy.

## <a name="example"></a>Przykład

```cpp
//   Specify single-inheritance only
#pragma pointers_to_members( full_generality, single_inheritance )
```

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
