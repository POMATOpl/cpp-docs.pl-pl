---
title: "Porady: konwertowanie kontenera STL/CLR na kolekcję .NET | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aa58c8db46d1443ca5b39449222cc22e31eafb5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>Porady: konwertowanie kontenera STL/CLR na kolekcję .NET
W tym temacie przedstawiono sposób Konwertuj kontenery STL/CLR na ich równoważne kolekcji .NET. Na przykład zostanie przedstawiony sposób konwertowania STL/CLR [wektor](../dotnet/vector-stl-clr.md) do .NET <xref:System.Collections.Generic.ICollection%601> oraz sposobach przekształcania STL/CLR [mapy](../dotnet/map-stl-clr.md) do .NET <xref:System.Collections.Generic.IDictionary%602>, ale procedura jest podobnych dla wszystkich zbiorów i kontenery.  
  
### <a name="to-create-a-collection-from-a-container"></a>Aby utworzyć kolekcję z kontenera  
  
1.  Użyj jednej z następujących metod:  
  
    -   Aby przekonwertować częścią kontenera, należy wywołać [make_collection —](../dotnet/make-collection-stl-clr.md) funkcji i przekaż iteratora begin i iteratora zakończenia kontenera STL/CLR, które ma zostać skopiowany do kolekcji .NET. Ta funkcja szablonu przyjmuje iteratora STL/CLR jako argument szablonu. W pierwszym przykładzie pokazano tej metody.  
  
    -   Aby przekonwertować całego kontenera, rzutowania kontenera odpowiedni interfejs kolekcji .NET lub interfejs kolekcji. W drugim przykładzie pokazano tej metody.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie tworzymy STL/CLR `vector` i Dodaj do niej elementy 5. Następnie utworzymy kolekcji .NET przez wywołanie metody `make_collection` funkcji. Na koniec wyświetli zawartość nowo utworzonej kolekcji.  
  
```  
// cliext_convert_vector_to_icollection.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/vector>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::vector<int> primeNumbersCont;  
    primeNumbersCont.push_back(2);  
    primeNumbersCont.push_back(3);  
    primeNumbersCont.push_back(5);  
    primeNumbersCont.push_back(7);  
    primeNumbersCont.push_back(11);  
  
    System::Collections::Generic::ICollection<int> ^iColl =  
        make_collection<cliext::vector<int>::iterator>(  
            primeNumbersCont.begin() + 1,  
            primeNumbersCont.end() - 1);  
  
    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");  
    for each (int i in iColl)  
    {  
        Console::WriteLine(i);  
    }  
}  
```  
  
```Output  
The contents of the System::Collections::Generic::ICollection are:  
3  
5  
7  
```  
  
## <a name="example"></a>Przykład  
 W tym przykładzie tworzymy STL/CLR `map` i Dodaj do niej elementy 5. Następnie utworzymy .NET <xref:System.Collections.Generic.IDictionary%602> i przypisz `map` bezpośrednio do niego. Na koniec wyświetli zawartość nowo utworzonej kolekcji.  
  
```  
// cliext_convert_map_to_idictionary.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/map>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;  
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));  
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));  
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));  
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));  
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));  
  
    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;  
  
    Console::WriteLine("The contents of the IDictionary are:");  
    for each (KeyValuePair<float, int> ^kvp in iDict)  
    {  
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);  
    }  
}  
```  
  
```Output  
The contents of the IDictionary are:  
Key: 0.00 Value: 0  
Key: 13.00 Value: 13  
Key: 22.00 Value: 22  
Key: 42.00 Value: 42  
Key: 74.00 Value: 74  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do biblioteki STL/CLR](../dotnet/stl-clr-library-reference.md)   
 [Porady: konwertowanie kolekcji .NET na kontener STL/CLR](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)   
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)