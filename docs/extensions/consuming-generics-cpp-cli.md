---
title: Konsumowanie typów ogólnych (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- generics [C++], consuming from .NET languages
ms.assetid: e6330ef5-e907-432e-b527-7a22f5899639
ms.openlocfilehash: a4307213341ff7c20be273e52aa4d44dee926e84
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912801"
---
# <a name="consuming-generics-ccli"></a>Konsumowanie typów ogólnych (C++/CLI)

Typy ogólne utworzone w jednym języku .NET (lub platformy UWP) mogą być używane w innych językach. W przeciwieństwie do szablonów, ogólna w skompilowanym zestawie nadal pozostaje ogólna. W ten sposób jeden może tworzyć wystąpienia typu ogólnego w innym zestawie, a nawet w innym języku niż zestaw, w którym zdefiniowano typ ogólny.

## <a name="example"></a>Przykład

### <a name="description"></a>Opis

Ten przykład pokazuje klasę generyczną zdefiniowaną C#w elemencie.

### <a name="code"></a>Kod

```csharp
// consuming_generics_from_other_NET_languages.cs
// compile with: /target:library
// a C# program
public class CircularList<ItemType> {
   class ListNode    {
      public ItemType m_item;
      public ListNode next;
      public ListNode(ItemType item) {
         m_item = item;
      }
   }

   ListNode first, last;

   public CircularList() {}

   public void Add(ItemType item) {
      ListNode newnode = new ListNode(item);
      if (first == null) {
         first = last = newnode;
         first.next = newnode;
         last.next = first;
      }
      else {
         newnode.next = first;
         first = newnode;
         last.next = first;
      }
   }

   public void Remove(ItemType item) {
      ListNode iter = first;
      if (first.m_item.Equals( item )) {
         first =
         last.next = first.next;
      }
      for ( ; iter != last ; iter = iter.next )
         if (iter.next.m_item.Equals( item )) {
              if (iter.next == last)
                  last = iter;
              iter.next = iter.next.next;
              return;
          }
   }

   public void PrintAll() {
      ListNode iter = first;
      do {
         System.Console.WriteLine( iter.m_item );
         iter = iter.next;
      } while (iter != last);
   }
}
```

## <a name="example"></a>Przykład

### <a name="description"></a>Opis

Ten przykład korzysta z zestawu, który został utworzony C#w.

### <a name="code"></a>Kod

```cpp
// consuming_generics_from_other_NET_languages_2.cpp
// compile with: /clr
#using <consuming_generics_from_other_NET_languages.dll>
using namespace System;
class NativeClass {};
ref class MgdClass {};

int main() {
   CircularList<int>^ circ1 = gcnew CircularList<int>();
   CircularList<MgdClass^>^ circ2 = gcnew CircularList<MgdClass^>();

   for (int i = 0 ; i < 100 ; i += 10)
      circ1->Add(i);
   circ1->Remove(50);
   circ1->PrintAll();
}
```

```Output
90
80
70
60
40
30
20
10
```

## <a name="see-also"></a>Zobacz także

[Typy ogólne](generics-cpp-component-extensions.md)