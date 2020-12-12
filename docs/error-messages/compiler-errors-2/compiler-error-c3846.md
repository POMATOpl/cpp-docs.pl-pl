---
description: 'Dowiedz się więcej o: błąd kompilatora C3846'
title: Błąd kompilatora C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: 13c9cb7a9dde3710cac31d8ee79fb148f8ff67bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255395"
---
# <a name="compiler-error-c3846"></a>Błąd kompilatora C3846

"symbol": nie można zaimportować symbolu z "Assembly2": ponieważ "symbol" został już zaimportowany z innego zestawu "assembly1"

Nie można zaimportować symbolu z przywoływanego zestawu, ponieważ został on poprzednio zaimportowany z przywoływanego zestawu.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3846:

```cpp
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

A następnie Skompiluj:

```cpp
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
