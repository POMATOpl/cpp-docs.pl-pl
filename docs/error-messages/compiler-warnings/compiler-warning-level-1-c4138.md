---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4138'
title: Ostrzeżenie kompilatora (poziom 1) C4138
ms.date: 11/04/2016
f1_keywords:
- C4138
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
ms.openlocfilehash: 68789c7300944c7435431688ff147f40cd4cadb0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278028"
---
# <a name="compiler-warning-level-1-c4138"></a>Ostrzeżenie kompilatora (poziom 1) C4138

znaleziono "*/" poza komentarzem

Ogranicznik komentarza zamykającego nie jest poprzedzony ogranicznikiem otwierającym komentarz. Kompilator zakłada spację między gwiazdką ( <strong>\*</strong> ) a ukośnikiem (/).

## <a name="example"></a>Przykład

```cpp
// C4138a.cpp
// compile with: /W1
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning
int main()
{
}
```

To ostrzeżenie może być spowodowane próbą zazagnieżdżania komentarzy.

To ostrzeżenie można rozwiązać w przypadku dodawania komentarzy do sekcji kodu, które zawierają komentarze, należy ująć kod w bloku **#if/#endif** i ustawić wyrażenie kontrolne na wartość zero:

```cpp
// C4138b.cpp
// compile with: /W1
#if 0
int my_variable;   /* Declaration currently not needed */
#endif
int main()
{
}
```
