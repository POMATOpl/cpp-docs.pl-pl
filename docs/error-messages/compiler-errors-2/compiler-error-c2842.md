---
description: 'Dowiedz się więcej o: błąd kompilatora C2842'
title: Błąd kompilatora C2842
ms.date: 11/04/2016
f1_keywords:
- C2842
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
ms.openlocfilehash: f086c6c5fcfa451f320d96470615e4f5f4d5674a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119986"
---
# <a name="compiler-error-c2842"></a>Błąd kompilatora C2842

> "*Class*": typ zarządzany lub WinRT nie może definiować własnego "operator new" ani "operator delete"

## <a name="remarks"></a>Uwagi

Możesz zdefiniować własny **operator new** lub **operator delete** , aby zarządzać alokacją pamięci na stercie natywnym. Jednak klasy referencyjne nie mogą definiować tych operatorów, ponieważ są one przydzielane tylko na zarządzanej stercie.

Aby uzyskać więcej informacji, zobacz [Operatory zdefiniowane przez użytkownika (C++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C2842.

```cpp
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```
