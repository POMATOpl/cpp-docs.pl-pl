---
title: Błąd kompilatora C2660
ms.date: 11/04/2016
f1_keywords:
- C2660
helpviewer_keywords:
- C2660
ms.assetid: 2e01a1db-4f00-4df6-a04d-cb6f70a6922b
ms.openlocfilehash: 3f236f18faa92df660ed677df293373fe9f0800c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626697"
---
# <a name="compiler-error-c2660"></a>Błąd kompilatora C2660

'Funkcja': funkcja nie przyjmuje parametrów liczb

Funkcja jest wywoływana z niepoprawną liczbę parametrów.

C2660 może wystąpić, jeśli przypadkowo wywołania funkcji Windows API, a nie funkcją MFC element członkowski o takiej samej nazwie. Aby rozwiązać ten problem:

- Dostosuj wywołanie funkcji, aby były zgodne z formatem wywołanie funkcji elementu członkowskiego.

- Użyj operatora rozpoznawania zakresu (`::`) aby poinformować kompilator do wyszukania nazwy funkcji w przestrzeni nazw globalnego.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C2660.

```
// C2660.cpp
void func( int, int ) {}

int main() {
   func( 1 );   // C2660 func( int ) not declared
   func( 1, 0 );   // OK
}
```

## <a name="example"></a>Przykład

C2660 może również wystąpić, jeśli użytkownik podejmie próbę bezpośrednio wywołać metodę Dispose typu zarządzanego. Aby uzyskać więcej informacji, zobacz [destruktory i finalizatory](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers). Poniższy przykład spowoduje wygenerowanie C2660.

```
// C2660_a.cpp
// compile with: /clr
using namespace System;
using namespace System::Threading;

void CheckStatus( Object^ stateInfo ) {}

int main() {
   ManualResetEvent^ event = gcnew ManualResetEvent( false );
   TimerCallback^ timerDelegate = gcnew TimerCallback( &CheckStatus );
   Timer^ stateTimer = gcnew Timer( timerDelegate, event, 1000, 250 );

   stateTimer->Dispose();   // C2660
   stateTimer->~Timer();   // OK
}
```

## <a name="example"></a>Przykład

C2660 występuje, jeśli w klasie pochodnej ukrywa funkcję.

```
// C2660b.cpp
// C2660 expected
#include <stdio.h>

class f {
public:
   void bar() {
      printf_s("in f::bar\n");
    }
};

class f2 : public f {
public:
   void bar(int i){printf("in f2::bar\n");}
   // Uncomment the following line to resolve.
   // using f::bar;   // - using declaration added
   // or
   // void bar(){__super::bar();}
};

int main() {
   f2 fObject;
   fObject.bar();
}
```

## <a name="example"></a>Przykład

C2660 może wystąpić, jeśli wywołania z właściwości indeksowanej.

```
// C2660c.cpp
// compile with: /clr
ref class X {
   double d;
public:
   X() : d(1.9) {}
   property double MyProp[] {
      double get(int i) {
         return d;
      }
   }   // end MyProp definition
};

int main() {
   X ^ MyX = gcnew X();
   System::Console::WriteLine(MyX->MyProp(1));   // C2660
   System::Console::WriteLine(MyX->MyProp[1]);   // OK
}
```

## <a name="example"></a>Przykład

C2660 może wystąpić, jeśli wywołania z właściwości indeksowanej.

```
// C2660d.cpp
// compile with: /clr
ref class A{
public:
   property int default[int,int] {
      int get(int a, int b) {
         return a + b;
      }
   }
};

int main() {
   A^ a = gcnew A;
   int x = a[3][5];   // C2660
   int x2 = a[3,5];   // OK
}
```

## <a name="example"></a>Przykład

C2660 może wystąpić, jeśli zdefiniujesz nowy operator w klasą szablonu, ale w przypadku, gdy new operator tworzy obiekt, którego typ jest inny niż typ otaczający.

```
// C2660e.cpp
// compile with: /c
#include <malloc.h>

template <class T> class CA {
private:
    static T** line;
   void* operator new (size_t, int i) {
      return 0;
   }
   void operator delete(void* pMem, int i) {
      free(pMem);
   }

public:
   CA () { new (1) T(); }   // C2660
   // try the following line instead
   // CA () { new (1) CA<int>(); }
};

typedef CA <int> int_CA;

void AAA() {
   int_CA  list;
}
```