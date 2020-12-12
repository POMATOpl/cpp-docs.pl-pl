---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4399'
title: Ostrzeżenie kompilatora (poziom 1) C4399
ms.date: 11/04/2016
f1_keywords:
- C4399
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
ms.openlocfilehash: a1d0fab62d13c08fb2117279d9173786c65d846f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311139"
---
# <a name="compiler-warning-level-1-c4399"></a>Ostrzeżenie kompilatora (poziom 1) C4399

> "*symbol*": symbol dla procesu nie powinien być oznaczony przy użyciu __declspec (dllimport), gdy jest kompilowany z/CLR: Pure

## <a name="remarks"></a>Uwagi

**/CLR: Pure** kompilator Option jest przestarzały w programie visual Studio 2015 i nieobsługiwany w programie visual Studio 2017.

Dane z obrazu natywnego lub obrazu z konstrukcjami macierzystymi i CLR nie mogą zostać zaimportowane do czystego obrazu. Aby rozwiązać ten problem, skompiluj z **/CLR** (nie **/CLR: Pure**) ani Delete `__declspec(dllimport)` .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4399.

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```
