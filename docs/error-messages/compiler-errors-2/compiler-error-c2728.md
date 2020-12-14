---
description: 'Dowiedz się więcej o: błąd kompilatora C2728'
title: Błąd kompilatora C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: 7ef24dd037f8d765c072a61320da64411248dbc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245307"
---
# <a name="compiler-error-c2728"></a>Błąd kompilatora C2728

"Type": natywna tablica nie może zawierać tego typu

Składnia tworzenia tablicy została użyta do utworzenia tablicy obiektów zarządzanych lub WinRT. Nie można utworzyć tablicy obiektów zarządzanych lub WinRT przy użyciu natywnej składni tablicy.

Aby uzyskać więcej informacji, zobacz [Array](../../extensions/arrays-cpp-component-extensions.md).

Poniższy przykład generuje C2728 i pokazuje, jak to naprawić:

```cpp
// C2728.cpp
// compile with: /clr

int main() {
   int^ arr[5];   // C2728

   // try the following line instead
   array<int>^arr2;
}
```
