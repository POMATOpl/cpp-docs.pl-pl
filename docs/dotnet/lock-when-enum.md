---
title: Wyliczenie lock_when
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::lock_when
- msclr.lock_when
- lock_when
helpviewer_keywords:
- lock_when enum
ms.assetid: 6b87bbe9-63cd-450d-a02e-bb91ffd0dcea
ms.openlocfilehash: be75ec497dff79d75c22bda3b7d24389db2c9c59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153242"
---
# <a name="lockwhen-enum"></a>Wyliczenie lock_when

Określa odroczonego blokowania.

## <a name="syntax"></a>Składnia

```
enum lock_when {
   lock_later
};
```

## <a name="remarks"></a>Uwagi

Gdy przekazywane do [lock::lock](../dotnet/lock-lock.md), `lock_later` Określa, czy blokada nie uwzględnia się teraz.

## <a name="example"></a>Przykład

W tym przykładzie użycie pojedynczego wystąpienia klasy przez wiele wątków.  Klasa stosowana jest blokada na siebie, aby upewnić się, że dostęp do jego wewnętrznych danych są spójne dla każdego wątku.  Głównego wątku aplikacji stosowana jest blokada na tym samym wystąpieniu klasy mogą okresowo sprawdzać, czy wszystkie wątki robocze nadal istnieje, i czeka, aby zakończyć pracę, dopóki wszystkie wątki robocze zostały wykonane ich zadań.

```
// msl_lock_lock_when.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="requirements"></a>Wymagania

**Plik nagłówkowy** \<msclr\lock.h >

**Namespace** msclr

## <a name="see-also"></a>Zobacz także

[lock](../dotnet/lock.md)
