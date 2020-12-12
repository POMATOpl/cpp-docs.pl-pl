---
description: 'Dowiedz się więcej o: błąd kompilatora C3813'
title: Błąd kompilatora C3813
ms.date: 11/04/2016
f1_keywords:
- C3813
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
ms.openlocfilehash: ae7157166083a4a86d9a5b170cbff3e127c87abb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180997"
---
# <a name="compiler-error-c3813"></a>Błąd kompilatora C3813

Deklaracja właściwości może wystąpić tylko w definicji typu zarządzanego lub WinRT

[Właściwość](../../dotnet/how-to-use-properties-in-cpp-cli.md) może być zadeklarowana tylko w typie zarządzanym lub środowisko wykonawcze systemu Windows. Typy natywne nie obsługują **`property`** słowa kluczowego.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3813 i pokazuje, jak to naprawić:

```cpp
// C3813.cpp
// compile by using: cl /c /clr C3813.cpp
class A
{
   property int Int; // C3813
};

ref class B
{
   property int Int; // OK - declared within managed type
};
```
