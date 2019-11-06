---
title: Ostrzeżenie kompilatora (poziom 1) C4227
ms.date: 11/04/2016
f1_keywords:
- C4227
helpviewer_keywords:
- C4227
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
ms.openlocfilehash: aea4d082b21d59aa430befd89d2032fb7ebc0e65
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627285"
---
# <a name="compiler-warning-level-1-c4227"></a>Ostrzeżenie kompilatora (poziom 1) C4227

anachronizm użyte: kwalifikatory dla odwołania są ignorowane

Używanie kwalifikatorów, takich jak `const` lub C++ `volatile` z odwołaniami, jest nieaktualnym postępowaniem.

## <a name="example"></a>Przykład

```cpp
// C4227.cpp
// compile with: /W1 /c
int j = 0;
int &const i = j;   // C4227
```