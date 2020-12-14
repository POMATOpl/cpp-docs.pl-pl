---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4125'
title: Ostrzeżenie kompilatora (poziom 4) C4125
ms.date: 11/04/2016
f1_keywords:
- C4125
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
ms.openlocfilehash: 82c94743e2ff52efacdf1b5f139bc4d9d40d0eed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261921"
---
# <a name="compiler-warning-level-4-c4125"></a>Ostrzeżenie kompilatora (poziom 4) C4125

cyfra dziesiętna kończy ósemkową sekwencję ucieczki

Kompilator oblicza liczbę ósemkową bez cyfry dziesiętnej i zakłada, że cyfra dziesiętna jest znakiem.

## <a name="example"></a>Przykład

```cpp
// C4125a.cpp
// compile with: /W4
char array1[] = "\709"; // C4125
int main()
{
}
```

Jeśli cyfra 9 jest zamierzona jako znak, należy poprawić przykład w następujący sposób:

```cpp
// C4125b.cpp
// compile with: /W4
char array[] = "\0709";  // C4125 String containing "89"
int main()
{
}
```
