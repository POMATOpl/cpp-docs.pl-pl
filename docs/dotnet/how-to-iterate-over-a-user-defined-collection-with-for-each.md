---
title: 'Instrukcje: dla każdej iteracji po kolekcji zdefiniowanych przez użytkownika z | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- collections, iterating over
ms.assetid: 0efd9e3c-d7bb-4f6c-9938-e0e65d191433
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d3556faac731b11e4933126e8890304d3878d7d6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422756"
---
# <a name="how-to-iterate-over-a-user-defined-collection-with-for-each"></a>Porady: iterowanie przez kolekcję zdefiniowaną przez użytkownika za pomocą instrukcji for each

Klasa może być zarządzana Kolekcja musi ona funkcję GetEnumerator nieprywatny, która zwraca uchwyt do modułu wyliczającego klasę lub interfejs.  Klasa modułu wyliczającego musi zawierać deklaracji pod kątem funkcji MoveNext niestatyczna i bieżącą właściwość typu.

## <a name="example"></a>Przykład

Proste użytkownika zdefiniowane kolekcji w przypadku typów referencyjnych.

```
// for_each_user_defined_collections.cpp
// compile with: /clr
using namespace System;
public interface struct IMyEnumerator {
   bool MoveNext();
   property Object^ Current {
      Object^ get();
   }
   void Reset();
};

public ref struct MyArray {

   MyArray( array<int>^ d ) {
      data = d;
   }

   ref struct enumerator : IMyEnumerator {
      enumerator( MyArray^ myArr ) {
         colInst = myArr;
         currentIndex = -1;
      }

      virtual bool MoveNext() {
         if( currentIndex < colInst->data->Length - 1 ) {
            currentIndex++;
            return true;
         }
         return false;
      }

      property Object^ Current {
         virtual Object^ get() {
            return colInst->data[currentIndex];
         }
      };

      virtual void Reset() {}
      ~enumerator() {}

      MyArray^ colInst;
      int currentIndex;
   };

   array<int>^ data;

   IMyEnumerator^ GetEnumerator() {
      return gcnew enumerator(this);
   }
};

int main() {
   int retval = 0;

   MyArray^ col = gcnew MyArray( gcnew array<int>{10, 20, 30 } );

   for each ( Object^ c in col )
      retval += (int)c;

   retval -= 10 + 20 + 30;

   for each ( int c in gcnew MyArray( gcnew array<int>{10, 20, 30 } ) )
      retval += c;

   retval -= 10 + 20 + 30;

   Console::WriteLine("Return Code: {0}", retval );
   return retval;
}
```

```Output
Return Code: 0
```

## <a name="see-also"></a>Zobacz też

[for each, in](../dotnet/for-each-in.md)