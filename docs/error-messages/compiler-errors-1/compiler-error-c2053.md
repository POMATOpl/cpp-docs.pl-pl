---
description: 'Dowiedz się więcej o: błąd kompilatora C2053'
title: Błąd kompilatora C2053
ms.date: 11/04/2016
f1_keywords:
- C2053
helpviewer_keywords:
- C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
ms.openlocfilehash: 6ead23c4a32e2f781bbc070284d6c83118e0c569
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283722"
---
# <a name="compiler-error-c2053"></a>Błąd kompilatora C2053

"Identyfikator": niezgodność ciągu szerokiego

Ciąg szeroki jest przypisany do niezgodnego typu.

Poniższy przykład generuje C2053:

```c
// C2053.c
int main() {
   char array[] = L"Rika";   // C2053
}
```
