---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 2) C4302'
title: Ostrzeżenie kompilatora (poziom 2) C4302
ms.date: 11/04/2016
f1_keywords:
- C4302
helpviewer_keywords:
- C4302
ms.assetid: f5e1c939-e134-4cca-ba1e-9b15a81549ae
ms.openlocfilehash: 0be91208d62c06882713d6b00358665f518103fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173561"
---
# <a name="compiler-warning-level-2-c4302"></a>Ostrzeżenie kompilatora (poziom 2) C4302

"Conversion": obcinanie z "Type 1" do "Type 2"

Kompilator wykrył konwersję z większego typu do mniejszego typu. Informacje mogą zostać utracone.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Poniższy przykład generuje C4302:

```cpp
// C4302.cpp
// compile with: /W2
#pragma warning(default : 4302)
int main() {
   int i;
   char c = (char) &i;     // C4302
   short s = (short) &i;   // C4302
}
```
