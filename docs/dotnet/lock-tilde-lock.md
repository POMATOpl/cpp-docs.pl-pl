---
title: 'Zablokuj:: ~ lock | Dokumentacja firmy Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ~lock
- msclr.lock.~lock
- lock.~lock
- msclr::lock::~lock
- lock::~lock
dev_langs: C++
helpviewer_keywords: ~lock destructor
ms.assetid: 55fa9f6c-d7a6-48ef-9236-ee03342c1d20
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f81ebc097d53029dc4d4e161c9cf43e15e37b94d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="locklock"></a>lock::~lock
Destructs `lock` obiektu.  
  
## <a name="syntax"></a>Składnia  
  
```  
~lock();  
```  
  
## <a name="remarks"></a>Uwagi  
 Wywołania destruktora [lock::release](../dotnet/lock-release.md).  
  
## <a name="example"></a>Przykład  
 W tym przykładzie użycie pojedynczego wystąpienia klasy przez wiele wątków.  Klasy używa blokady na samym sobie, aby upewnić się, że dostęp do swoich danych wewnętrznych są spójne dla każdego wątku.  Wątku głównego aplikacji nawiązywał blokady dla tego samego wystąpienia klasy okresowo sprawdzać, czy wszystkie wątki robocze nadal istnieje i czeka, aby wyjść do wszystkich wątków zakończył ich zadań.  
  
```  
// msl_lock_dtor.cpp  
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
 **Plik nagłówka** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Zobacz też  
 [elementy członkowskie Lock](../dotnet/lock-members.md)   
 [lock::lock](../dotnet/lock-lock.md)