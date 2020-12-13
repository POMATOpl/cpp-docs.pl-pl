---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4291'
title: Ostrzeżenie kompilatora (poziom 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: 190fbb1ed91c5524dcd83a0a02a0b0280e264891
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340115"
---
# <a name="compiler-warning-level-1-c4291"></a>Ostrzeżenie kompilatora (poziom 1) C4291

"Deklaracja": nie znaleziono pasującego operatora delete; pamięć nie zostanie zwolniona, jeśli Inicjalizacja zgłosi wyjątek

Zostanie użyte [nowe](../../cpp/new-operator-cpp.md) miejsce umieszczenia, dla którego nie ma żadnego [usunięcia](../../cpp/delete-operator-cpp.md)umieszczania.

Po przydzieleniu pamięci dla obiektu z operatorem **`new`** wywoływana jest Konstruktor obiektu. Jeśli Konstruktor zgłasza wyjątek, wszystkie pamięci, które zostały przydzieloną dla tego obiektu, powinny zostać cofnięte. Nie można tego zrobić, chyba że **`delete`** istnieje funkcja operatora zgodna z operatorem **`new`** .

W przypadku użycia operatora **`new`** bez dodatkowych argumentów i kompilowania z opcjami [/GX](../../build/reference/gx-enable-exception-handling.md), [/EHS](../../build/reference/eh-exception-handling-model.md)lub/EHa w celu włączenia obsługi wyjątków, kompilator generuje kod do operatora wywołania, **`delete`** Jeśli Konstruktor zgłosi wyjątek.

Jeśli używasz formy umieszczania **`new`** operatora (formularz z argumentami (oprócz rozmiaru alokacji), a Konstruktor obiektu zgłasza wyjątek, kompilator nadal będzie generował kod do wywołania operatora, **`delete`** ale tylko wtedy, gdy formularz położenia operatora **`delete`** istnieje, zgodny z formularzem umieszczania operatora **`new`** , który przydzielił pamięć. Na przykład:

```cpp
// C4291.cpp
// compile with: /EHsc /W1
#include <malloc.h>

class CList
{
public:
   CList(int)
   {
      throw "Fail!";
   }
};

void* operator new(size_t size, char* pszFilename, int nLine)
{
   return malloc(size);
}

int main(void)
{
   try
   {
      // This will call ::operator new(unsigned int) to allocate heap
      // memory. Heap memory pointed to by pList1 will automatically be
      // deallocated by a call to ::operator delete(void*) when
      // CList::CList(int) throws an exception.
      CList* pList1 = new CList(10);
   }
   catch (...)
   {
   }

   try
   {
      // This will call the overloaded ::operator new(size_t, char*, int)
      // to allocate heap memory. When CList::CList(int) throws an
      // exception, ::operator delete(void*, char*, int) should be called
      // to deallocate the memory pointed to by pList2. Since
      // ::operator delete(void*, char*, int) has not been implemented,
      // memory will be leaked when the deallocation cannot occur.
      CList* pList2 = new(__FILE__, __LINE__) CList(20);   // C4291
   }
   catch (...)
   {
   }
}
```

Powyższy przykład generuje ostrzeżenie C4291, ponieważ nie zdefiniowano formy umieszczania operatora **`delete`** , która pasuje do formy położenia operatora **`new`** . Aby rozwiązać ten problem, Wstaw poniższy kod powyżej **Main**. Należy zauważyć, że wszystkie parametry funkcji przeciążonego operatora **`delete`** są zgodne z tymi, które są przeciążone operatora **`new`** , z wyjątkiem pierwszego parametru.

```cpp
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```
