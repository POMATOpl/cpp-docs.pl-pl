---
title: Zaprzyjaźnione szablony | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 077acea5-0d0f-4b33-916d-1211797e5e28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97447189419bad8d3ad6f2026a7ee5f701ebca04
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466959"
---
# <a name="template-friends"></a>Zaprzyjaźnione szablony

Szablony klas mogą posiadać [znajomych](friend-cpp.md). Klasa, szablon klasy, funkcja lub szablon funkcji może być elementem zaprzyjaźnionym dla klasy szablonu. Elementy zaprzyjaźnione mogą być także specjalizacjami szablonu klasy lub szablonu funkcji, ale nie specjalizacjami częściowymi.  
  
**C ++ 11**: parametr typu mogą być deklarowane jako zaprzyjaźniona za pomocą formularza `friend T;`.  
  
```cpp
template <typename T>  
class my_class  
{  
    friend T;  
    //...  
};  
```  
  
## <a name="example"></a>Przykład

W poniższym przykładzie, funkcja zaprzyjaźniona jest zdefiniowana jako szablon funkcji w ramach szablonu klasy. Ten kod tworzy wersję funkcji zaprzyjaźnionej dla każdego wystąpienia szablonu. Ta konstrukcja jest przydatna, gdy funkcja zaprzyjaźniona zależy od tych samych parametrów szablonu, co klasa.  
  
```cpp
// template_friend1.cpp  
// compile with: /EHsc  
  
#include <iostream>  
using namespace std;  
  
template <class T> class Array {  
   T* array;  
   int size;  
  
public:  
   Array(int sz): size(sz) {  
      array = new T[size];  
      memset(array, 0, size * sizeof(T));  
   }  
  
   Array(const Array& a) {  
      size = a.size;  
      array = new T[size];  
      memcpy_s(array, a.array, sizeof(T));  
   }  
  
   T& operator[](int i) {  
      return *(array + i);  
   }  
  
   int Length() { return size; }  
  
   void print() {  
      for (int i = 0; i < size; i++)        
         cout << *(array + i) << " ";  
  
      cout << endl;  
   }  
  
   template<class T>  
   friend Array<T>* combine(Array<T>& a1, Array<T>& a2);  
};  
  
template<class T>  
Array<T>* combine(Array<T>& a1, Array<T>& a2) {  
   Array<T>* a = new Array<T>(a1.size + a2.size);  
   for (int i = 0; i < a1.size; i++)  
      (*a)[i] = *(a1.array + i);  
  
   for (int i = 0; i < a2.size; i++)  
      (*a)[i + a1.size] = *(a2.array + i);  
  
   return a;  
}  
  
int main() {  
   Array<char> alpha1(26);  
   for (int i = 0 ; i < alpha1.Length() ; i++)  
      alpha1[i] = 'A' + i;  
  
   alpha1.print();  
  
   Array<char> alpha2(26);  
   for (int i = 0 ; i < alpha2.Length() ; i++)  
      alpha2[i] = 'a' + i;  
  
   alpha2.print();  
   Array<char>*alpha3 = combine(alpha1, alpha2);  
   alpha3->print();  
   delete alpha3;  
}  
```  
  
```Output
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z   
a b c d e f g h i j k l m n o p q r s t u v w x y z   
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z a b c d e f g h i j k l m n o p q r s t u v w x y z   
```  
  
## <a name="example"></a>Przykład  

Następny przykład zawiera element zaprzyjaźniony, który posiada specjalizację szablonu. Specjalizacja szablonu funkcji jest automatycznie zaprzyjaźniona, jeśli oryginalny szablon funkcji jest zaprzyjaźniony.  
  
Możliwe jest także zadeklarowanie specjalizowanej wersji szablonu w formie zaprzyjaźnionej, jak wskazuje komentarz przed deklaracją elementu zaprzyjaźnionego w poniższym kodzie. Jeśli to zrobisz, należy umieścić definicję specjalizacji szablonu zaprzyjaźnionego poza klasą szablonu.  
  
```cpp
// template_friend2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
template <class T>  
class Array;  
  
template <class T>  
void f(Array<T>& a);  
  
template <class T> class Array  
{  
    T* array;  
    int size;  
  
public:  
    Array(int sz): size(sz)  
    {  
        array = new T[size];  
        memset(array, 0, size * sizeof(T));  
    }  
    Array(const Array& a)  
    {  
        size = a.size;  
        array = new T[size];  
        memcpy_s(array, a.array, sizeof(T));  
    }  
    T& operator[](int i)  
    {  
        return *(array + i);  
    }  
    int Length()  
    {   
        return size;  
    }  
    void print()  
    {  
        for (int i = 0; i < size; i++)  
        {  
            cout << *(array + i) << " ";  
        }  
        cout << endl;  
    }  
    // If you replace the friend declaration with the int-specific  
    // version, only the int specialization will be a friend.  
    // The code in the generic f will fail  
    // with C2248: 'Array<T>::size' :  
    // cannot access private member declared in class 'Array<T>'.  
    //friend void f<int>(Array<int>& a);  
  
    friend void f<>(Array<T>& a);  
};  
  
// f function template, friend of Array<T>  
template <class T>  
void f(Array<T>& a)  
{  
    cout << a.size << " generic" << endl;  
}  
  
// Specialization of f for int arrays  
// will be a friend because the template f is a friend.  
template<> void f(Array<int>& a)  
{  
    cout << a.size << " int" << endl;  
}  
  
int main()  
{  
    Array<char> ac(10);  
    f(ac);  
  
    Array<int> a(10);  
    f(a);  
}  
```  

```Output
10 generic  
10 int  
```  
  
## <a name="example"></a>Przykład  
 
W następnym przykładzie pokazano szablon klasy zaprzyjaźnionej, zadeklarowany w ramach szablonu klasy. Szablon klasy jest następnie używany w postaci argumentu szablonu dla klasy zaprzyjaźnionej. Szablony klas zaprzyjaźnionych muszą być zdefiniowane poza szablonem klasy, w którym zostały zadeklarowane. Wszystkie specjalizacje lub częściowe specjalizacje zaprzyjaźnionego szablonu są również zaprzyjaźnionymi elementami oryginalnego szablonu klasy.  
  
```cpp  
// template_friend3.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
template <class T>  
class X  
{  
private:  
   T* data;  
   void InitData(int seed) { data = new T(seed); }  
public:  
   void print() { cout << *data << endl; }  
   template <class U> friend class Factory;  
};  
  
template <class U>  
class Factory  
{  
public:  
   U* GetNewObject(int seed)  
   {  
      U* pu = new U;  
      pu->InitData(seed);  
      return pu;  
   }  
};  
  
int main()  
{  
   Factory< X<int> > XintFactory;  
   X<int>* x1 = XintFactory.GetNewObject(65);  
   X<int>* x2 = XintFactory.GetNewObject(97);  
  
   Factory< X<char> > XcharFactory;  
   X<char>* x3 = XcharFactory.GetNewObject(65);  
   X<char>* x4 = XcharFactory.GetNewObject(97);  
   x1->print();  
   x2->print();  
   x3->print();  
   x4->print();  
}  
```  

```Output 
65  
97  
A  
a  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Argumenty domyślne](../cpp/default-arguments.md)