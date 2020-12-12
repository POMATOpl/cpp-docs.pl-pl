---
description: 'Dowiedz się więcej o: błąd kompilatora C2850'
title: Błąd kompilatora C2850
ms.date: 11/04/2016
f1_keywords:
- C2850
helpviewer_keywords:
- C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
ms.openlocfilehash: 820aa0e12db5ffe7e6d7b7bf0e87282f53e8477c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260166"
---
# <a name="compiler-error-c2850"></a>Błąd kompilatora C2850

"konstrukcja": dozwolone tylko w zakresie pliku; nie może znajdować się w zagnieżdżonej konstrukcji

Konstrukcje, takie jak dyrektywy pragma, mogą występować tylko w zakresie globalnym.

Poniższy przykład generuje C2850:

```cpp
// C2850.cpp
// compile with: /c /Yc
// try the following line instead
// #pragma hdrstop
namespace X {
   #pragma hdrstop   // C2850
};
```
