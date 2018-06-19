---
title: 'Porady: Użyj odwołań śledzenia w języku C + +/ CLI | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CLR types, passing by reference
ms.assetid: d91e471c-34ff-4786-9e0d-c6db0494b946
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a6d14db826182c82b44bc3bca3d686e38eaae85f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132469"
---
# <a name="how-to-use-tracking-references-in-ccli"></a>Porady: korzystanie z odwołań śledzenia w języku C++/interfejsie wiersza polecenia
W tym artykule przedstawiono sposób użycia odwołania śledzenia (%) w języku C + +/ CLI do przekazania wspólnego języka środowiska uruchomieniowego (języka wspólnego CLR) typów przez odwołanie.  
  
## <a name="to-pass-clr-types-by-reference"></a>Aby przekazać typów CLR przez odwołanie  
 Poniższy przykład przedstawia sposób użycia odwołanie śledzące do przekazywania typów CLR przez odwołanie.  
  
```cpp  
// tracking_reference_handles.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct City {  
private:  
   Int16 zip_;  
  
public:  
   City (int zip) : zip_(zip) {};  
   property Int16 zip {  
      Int16 get(void) {  
         return zip_;  
      }   // get  
   }   // property  
};  
  
void passByRef (City ^% myCity) {  
   // cast required so this pointer in City struct is "const City"  
   if (myCity->zip == 20100)  
      Console::WriteLine("zip == 20100");  
   else  
      Console::WriteLine("zip != 20100");  
}  
  
ref class G {  
public:  
   int i;  
};  
  
void Test(int % i) {  
   i++;  
}  
  
int main() {  
   G ^ g1 = gcnew G;  
   G ^% g2 = g1;  
   g1 -> i = 12;  
  
   Test(g2->i);   // g2->i will be changed in Test2()  
  
   City ^ Milano = gcnew City(20100);  
   passByRef(Milano);  
}  
```  
  
```Output  
zip == 20100  
```  
  
 Następna próbka pokazuje, że pobieranie adresu odwołania śledzenia zwraca [interior_ptr (C + +/ CLI)](../windows/interior-ptr-cpp-cli.md)oraz sposób modyfikowania i uzyskać dostęp do danych za pośrednictwem odwołaniem śledzącym.  
  
```cpp  
// tracking_reference_data.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class R {  
public:  
   R(int i) : m_i(i) {  
      Console::WriteLine("ctor: R(int)");  
   }  
  
   int m_i;  
};  
  
class N {  
public:  
   N(int i) : m_i (i) {  
      Console::WriteLine("ctor: N(int i)");  
   }  
  
   int m_i;  
};  
  
int main() {  
   R ^hr = gcnew R('r');  
   R ^%thr = hr;  
   N n('n');  
   N %tn = n;  
  
   // Declare interior pointers  
   interior_ptr<R^> iphr = &thr;  
   interior_ptr<N> ipn = &tn;  
  
   // Modify data through interior pointer  
   (*iphr)->m_i = 1;   // (*iphr)->m_i == thr->m_i  
   ipn->m_i = 4;   // ipn->m_i == tn.m_i  
  
   ++thr-> m_i;   // hr->m_i == thr->m_i  
   ++tn. m_i;   // n.m_i == tn.m_i  
  
   ++hr-> m_i;   // (*iphr)->m_i == hr->m_i  
   ++n. m_i;   // ipn->m_i == n.m_i  
}  
```  
  
```Output  
ctor: R(int)  
ctor: N(int i)  
```  
  
## <a name="tracking-references-and-interior-pointers"></a>Odwołania śledzenia i wskaźników wewnętrznych  
 Poniższy przykładowy kod pokazuje, że można konwertować między odwołań śledzenia i wskaźników wewnętrznych.  
  
```cpp  
// tracking_reference_interior_ptr.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class R {  
public:  
   R(int i) : m_i(i) {  
      Console::WriteLine("ctor: R(int)");  
   }  
  
   int m_i;  
};  
  
class N {  
public:  
   N(int i) : m_i(i) {  
      Console::WriteLine("ctor: N(int i)");  
   }  
  
   int m_i;  
};  
  
int main() {  
   R ^hr = gcnew R('r');  
   N n('n');  
  
   R ^%thr = hr;  
   N %tn = n;  
  
   // Declare interior pointers  
   interior_ptr<R^> iphr = &hr;  
   interior_ptr<N> ipn = &n;  
  
   // Modify data through interior pointer  
   (*iphr)->m_i = 1;   // (*iphr)-> m_i == thr->m_i  
   ipn->m_i = 4;   // ipn->m_i == tn.m_i  
  
   ++thr->m_i;   // hr->m_i == thr->m_i  
   ++tn.m_i;   // n.m_i == tn.m_i  
  
   ++hr->m_i;   // (*iphr)->m_i == hr->m_i  
   ++n.m_i;   // ipn->m_i == n.m_i  
}  
```  
  
```Output  
ctor: R(int)  
ctor: N(int i)  
```  
  
## <a name="tracking-references-and-value-types"></a>Odwołania śledzenia i typów wartości  
 W tym przykładzie pokazano prosty pakującej poprzez odwołanie śledzące do typu wartości:  
  
```cpp  
// tracking_reference_valuetypes_1.cpp
// compile with: /clr

using namespace System;

int main() {
   int i = 10;   
   int % j = i;   
   Object ^ o = j;   // j is implicitly boxed and assigned to o
}  
```  
  
 Następna próbka pokazuje, że może mieć zarówno odwołań śledzenia i natywnego odwołania do typów wartości.  
  
```cpp  
// tracking_reference_valuetypes_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   int i = 10;  
   int & j = i;  
   int % k = j;  
   i++;   // 11  
   j++;   // 12  
   k++;   // 13  
   Console::WriteLine(i);  
   Console::WriteLine(j);  
   Console::WriteLine(k);  
}  
```  
  
```Output  
13  
13  
13  
```  
  
 Poniższy przykład pokazuje, czy można użyć odwołania śledzenia wraz z typów wartości i typy natywne.  
  
```cpp  
// tracking_reference_valuetypes_3.cpp  
// compile with: /clr  
value struct G {  
   int i;  
};  
  
struct H {  
   int i;  
};  
  
int main() {  
   G g;  
   G % v = g;  
   v.i = 4;  
   System::Console::WriteLine(v.i);  
   System::Console::WriteLine(g.i);  
  
   H h;  
   H % w = h;  
   w.i = 5;  
   System::Console::WriteLine(w.i);  
   System::Console::WriteLine(h.i);  
}  
```  
  
```Output  
4  
4  
5  
5  
```  
  
 W tym przykładzie pokazano, czy można powiązać odwołanie śledzące do typu wartości na stercie zbierane pamięci:  
  
```cpp  
// tracking_reference_valuetypes_4.cpp  
// compile with: /clr  
using namespace System;  
value struct V {  
   int i;  
};  
  
void Test(V^ hV) {   // hv boxes another copy of original V on GC heap  
   Console::WriteLine("Boxed new copy V: {0}", hV->i);  
}  
  
int main() {  
   V v;   // V on the stack  
   v.i = 1;  
   V ^hV1 = v;   // v is boxed and assigned to hV1  
   v.i = 2;  
   V % trV = *hV1;   // trV is bound to boxed v, the v on the gc heap.  
   Console::WriteLine("Original V: {0}, Tracking reference to boxed V: {1}", v.i, trV.i);  
   V ^hV2 = trV;   // hv2 boxes another copy of boxed v on the GC heap  
   hV2->i = 3;  
   Console::WriteLine("Tracking reference to boxed V: {0}", hV2->i);  
   Test(trV);  
   v.i = 4;  
   V ^% trhV = hV1;  // creates tracking reference to boxed type handle  
   Console::WriteLine("Original V: {0}, Reference to handle of originally boxed V: {1}", v.i, trhV->i);  
}  
```  
  
```Output  
Original V: 2, Tracking reference to boxed V: 1  
Tracking reference to boxed V: 3  
Boxed new copy V: 1  
Original V: 4, Reference to handle of originally boxed V: 1  
```  
  
## <a name="template-functions-that-take-native-value-or-reference-parameters"></a>Funkcji szablonów, które przyjmują macierzystym, wartość lub parametrów odwołania  
 Za pomocą odwołania śledzenia w sygnaturze funkcji szablonu, można zapewnić, że funkcja może być wywoływany przez parametr typu macierzystego, wartości CLR lub odwołanie do środowiska CLR.  
  
```cpp  
// tracking_reference_template.cpp  
// compile with: /clr  
using namespace System;  
  
class Temp {  
public:  
   // template functions  
   template<typename T>  
   static int f1(T% tt) {   // works for object in any location  
      Console::WriteLine("T %");  
      return 0;  
   }  
  
   template<typename T>  
   static int f2(T& rt) {   // won't work for object on the gc heap  
      Console::WriteLine("T &");  
      return 1;  
   }  
};  
  
// Class Definitions  
ref struct R {  
   int i;  
};  
  
int main() {  
   R ^hr = gcnew R;  
   int i = 1;  
  
   Temp::f1(i); // ok  
   Temp::f1(hr->i); // ok  
   Temp::f2(i); // ok  
  
   // error can't track object on gc heap with a native reference  
   // Temp::f2(hr->i);   
}  
```  
  
```Output  
T %  
T %  
T &  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Operator odwołania śledzenia](../windows/tracking-reference-operator-cpp-component-extensions.md)