---
description: 'Dowiedz się więcej o: błąd kompilatora C3697'
title: Błąd kompilatora C3697
ms.date: 11/04/2016
f1_keywords:
- C3697
helpviewer_keywords:
- C3697
ms.assetid: 2d3f63c4-b7f8-421d-a7a5-2bf17fd054f9
ms.openlocfilehash: 71b8a48cfe5be962c69dbc65730c1820d766f60d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228706"
---
# <a name="compiler-error-c3697"></a>Błąd kompilatora C3697

"kwalifikator": nie można użyć tego kwalifikatora na "^"

Dojście śledzenia (^) zostało zastosowane do kwalifikatora, dla którego nie została zaprojektowana.

Poniższy przykład generuje C3697:

```cpp
// C3697.cpp
// compile with: /clr
using namespace System;
int main() {
   String ^__restrict s;   // C3697
   String ^ s2;   // OK
}
```
