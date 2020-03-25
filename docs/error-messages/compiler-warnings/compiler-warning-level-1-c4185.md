---
title: Ostrzeżenie kompilatora (poziom 1) C4185
ms.date: 11/04/2016
f1_keywords:
- C4185
helpviewer_keywords:
- C4185
ms.assetid: 37e7063a-35b1-4e05-ae31-e811dced02b9
ms.openlocfilehash: 32da9c7758c00459056a5bbc002e2884cb3c0e3c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163445"
---
# <a name="compiler-warning-level-1-c4185"></a>Ostrzeżenie kompilatora (poziom 1) C4185

ignorowanie nieznanego #import atrybutu "Attribute"

Atrybut nie jest prawidłowym atrybutem `#import`. Jest on ignorowany.

## <a name="example"></a>Przykład

```cpp
// C4185.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_such_attribute   // C4185
```
