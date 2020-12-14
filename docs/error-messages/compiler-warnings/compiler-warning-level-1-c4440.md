---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4440'
title: Ostrzeżenie kompilatora (poziom 1) C4440
ms.date: 11/04/2016
f1_keywords:
- C4440
helpviewer_keywords:
- C4440
ms.assetid: 78b9642a-a93e-401e-9d92-372f6451bc5d
ms.openlocfilehash: 9e0a126ea1461e0b98bcef5117b893ea232fe262
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311048"
---
# <a name="compiler-warning-level-1-c4440"></a>Ostrzeżenie kompilatora (poziom 1) C4440

Zignorowano ponowną definicję konwencji wywoływania z "calling_convention1" do "calling_convention2"

Próba zmiany konwencji wywoływania została zignorowana.

Poniższy przykład generuje C4440:

```cpp
// C4440.cpp
// compile with: /W1 /LD /clr
typedef void __clrcall F();
typedef F __cdecl *PFV;   // C4440
```
