---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4804'
title: Ostrzeżenie kompilatora (poziom 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: 0e1260df9327e714c487159b7c0c8c1a1168bad9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334910"
---
# <a name="compiler-warning-level-1-c4804"></a>Ostrzeżenie kompilatora (poziom 1) C4804

"Operation": niebezpieczne użycie typu "bool" w operacji

To ostrzeżenie dotyczy, gdy użyto **`bool`** zmiennej lub wartości w nieoczekiwany sposób. Na przykład C4804 jest generowany, jeśli używasz operatorów, takich jak ujemny operator jednoargumentowy ( **-** ) lub operator uzupełniania ( `~` ). Kompilator szacuje wyrażenie.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4804:

```cpp
// C4804.cpp
// compile with: /W1

int main()
{
   bool i = true;
   if (-i)   // C4804, remove the '-' to resolve
   {
      i = false;
   }
}
```
