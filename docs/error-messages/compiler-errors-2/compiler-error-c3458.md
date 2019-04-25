---
title: Compiler Error C3458
ms.date: 11/04/2016
f1_keywords:
- C3458
helpviewer_keywords:
- C3458
ms.assetid: 940202fd-8dcc-4042-9c96-3f9e9127d2f1
ms.openlocfilehash: 07749677dbaa84de205adf38aadee6867a553852
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222387"
---
# <a name="compiler-error-c3458"></a>Compiler Error C3458

"attribute1": atrybut "attribute2" jest już określona dla "konstrukcji"

Dla tego samego konstrukcji określono dwa atrybuty, które wzajemnie się wykluczają.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3458

```
// C3458.cpp
// compile with: /clr /c
[System::Reflection::DefaultMember("Chars")]
public ref class MyString {
public:
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3458
   property char default[int] {
      char get(int index);
      void set(int index, char c);
   }
};
```