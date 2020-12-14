---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4061'
title: Ostrzeżenie kompilatora (poziom 4) C4061
ms.date: 04/05/2019
f1_keywords:
- C4061
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
ms.openlocfilehash: 9e76fd864e57e6d84ed28b1646e8950186945d11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262064"
---
# <a name="compiler-warning-level-4-c4061"></a>Ostrzeżenie kompilatora (poziom 4) C4061

> moduł wyliczający "*Identifier*" w przełączniku *wyliczenia "enum" nie* jest jawnie obsługiwany przez etykietę case

Określony *Identyfikator* modułu wyliczającego nie ma skojarzonego programu obsługi w **`switch`** instrukcji, która ma **`default`** wielkość liter. Brakująca sprawa może być nadzorem lub może nie być przyczyną problemu. Może zależeć od tego, czy moduł wyliczający jest obsługiwany przez przypadek domyślny, czy nie. Aby uzyskać ostrzeżenie dotyczące nieużywanych modułów wyliczających w **`switch`** instrukcjach, które nie mają **`default`** wielkości liter, zobacz [C4062](compiler-warning-level-4-c4062.md).

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji o sposobie włączania ostrzeżeń, które są domyślnie wyłączone, zobacz [ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4061; Dodaj przypadek dla brakującego modułu wyliczającego, który ma zostać naprawiony:

```cpp
// C4061.cpp
// compile with: /W4
#pragma warning(default : 4061)

enum E { a, b, c };
void func ( E e )
{
   switch(e)
   {
      case a:
      case b:
      default:
         break;
   }   // C4061 c' not handled
}

int main()
{
}
```

## <a name="see-also"></a>Zobacz też

[Ostrzeżenie kompilatora (poziom 4) C4062](compiler-warning-level-4-c4062.md)
