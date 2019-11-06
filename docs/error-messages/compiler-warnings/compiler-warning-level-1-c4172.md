---
title: Ostrzeżenie kompilatora (poziom 1) C4172
ms.date: 11/04/2016
f1_keywords:
- C4172
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
ms.openlocfilehash: 7d53972dbcb2e3ab6a95b0b874cc6bb98cd66840
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624823"
---
# <a name="compiler-warning-level-1-c4172"></a>Ostrzeżenie kompilatora (poziom 1) C4172

Zwracanie adresu lokalnej zmiennej lub tymczasowej

Funkcja zwraca adres zmiennej lokalnej lub obiektu tymczasowego. Zmienne lokalne i obiekty tymczasowe są niszczone, gdy funkcja zwraca, więc zwrócony adres jest nieprawidłowy.

Przeprojektowanie funkcji tak, aby nie zwracała adresu obiektu lokalnego.

Poniższy przykład generuje C4172:

```cpp
// C4172.cpp
// compile with: /W1 /LD
float f = 10;

const double& bar() {
// try the following line instead
// const float& bar() {
   return f;   // C4172
}
```