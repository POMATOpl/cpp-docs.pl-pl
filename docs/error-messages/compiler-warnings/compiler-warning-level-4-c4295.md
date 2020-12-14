---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4295'
title: Ostrzeżenie kompilatora (poziom 4) C4295
ms.date: 01/09/2018
f1_keywords:
- C4295
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
ms.openlocfilehash: 77f94d96d7ce5659652296e814777341a310a19f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294590"
---
# <a name="compiler-warning-level-4-c4295"></a>Ostrzeżenie kompilatora (poziom 4) C4295

> "*Array*": tablica jest zbyt mała, aby można było uwzględnić kończący znak null

Tablica została zainicjowana, ale ostatni znak w tablicy nie jest wartością null. Uzyskiwanie dostępu do tablicy jako ciągu może spowodować uzyskanie nieoczekiwanych wyników.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4295. Aby rozwiązać ten problem, można zadeklarować większy rozmiar tablicy w celu przechowywania kończącego się wartości null z ciągu inicjatora lub można użyć listy inicjatora tablicy, aby określić, że jest to tablica **`char`** , a nie ciąg zakończony znakiem null.

```C
// C4295.c
// compile with: /W4

int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
