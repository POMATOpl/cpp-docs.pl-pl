---
description: 'Dowiedz się więcej na temat: jak uwidocznić kontener STL/CLR z zestawu'
title: 'Porady: uwidacznianie kontenera STL/CLR z zestawu'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, cross-assembly issues
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
ms.openlocfilehash: a4ed92af956def030c80f8f303f0a7501c4944c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134982"
---
# <a name="how-to-expose-an-stlclr-container-from-an-assembly"></a>Porady: uwidacznianie kontenera STL/CLR z zestawu

Kontenery STL/CLR, takie jak `list` i, `map` są implementowane jako klasy ref szablonu. Ponieważ szablony języka C++ są tworzone w czasie kompilacji, dwie klasy szablonów, które mają dokładnie taki sam podpis, ale znajdują się w różnych zestawach, są w rzeczywistości różne typy. Oznacza to, że klasy szablonów nie mogą być używane między granicami zestawu.

Aby umożliwić udostępnianie wielu zestawów, kontenery STL/CLR implementują interfejs generyczny <xref:System.Collections.Generic.ICollection%601> . Korzystając z tego interfejsu generycznego, wszystkie języki obsługujące typy ogólne, w tym C++, C# i Visual Basic, mogą uzyskiwać dostęp do kontenerów STL/CLR.

W tym temacie przedstawiono sposób wyświetlania elementów z kilku kontenerów STL/CLR, które są zapisywane w zestawie języka C++ o nazwie `StlClrClassLibrary` . Pokazujemy dwa zestawy, do których można uzyskać dostęp `StlClrClassLibrary` . Pierwszy zestaw jest zapisywana w języku C++, a drugi w języku C#.

Jeśli oba zestawy są zapisywane w języku C++, można uzyskać dostęp do ogólnego interfejsu kontenera przy użyciu jego `generic_container` typedef. Na przykład jeśli masz kontener typu `cliext::vector<int>` , jego ogólny interfejs to: `cliext::vector<int>::generic_container` . Podobnie można uzyskać iterator w interfejsie ogólnym przy użyciu `generic_iterator` typedef, jak w: `cliext::vector<int>::generic_iterator` .

Ponieważ te definicje są zadeklarowane w plikach nagłówkowych języka C++, nie można używać zestawów pisanych w innych językach. W związku z tym, aby uzyskać dostęp do interfejsu ogólnego `cliext::vector<int>` w języku C# lub innym języku .NET, użyj `System.Collections.Generic.ICollection<int>` . Aby wykonać iterację tej kolekcji, użyj `foreach` pętli.

Poniższa tabela zawiera listę ogólnych interfejsów, które implementuje każdy kontener STL/CLR:

|Kontener STL/CLR|Interfejs ogólny|
|------------------------|-----------------------|
|`deque<T>`|`ICollection<T>`|
|`hash_map<K, V>`|`IDictionary<K, V>`|
|`hash_multimap<K, V>`|`IDictionary<K, V>`|
|`hash_multiset<T>`|`ICollection<T>`|
|`hash_set<T>`|`ICollection<T>`|
|`list<T>`|`ICollection<T>`|
|`map<K, V>`|`IDictionary<K, V>`|
|`multimap<K, V>`|`IDictionary<K, V>`|
|`multiset<T>`|`ICollection<T>`|
|`set<T>`|`ICollection<T>`|
|`vector<T>`|`ICollection<T>`|

> [!NOTE]
> Ponieważ `queue` , `priority_queue` i `stack` kontenery nie obsługują iteratorów, nie implementują interfejsów ogólnych i nie można uzyskać dostępu do wielu zestawów.

## <a name="example-1"></a>Przykład 1

### <a name="description"></a>Opis

W tym przykładzie deklarujemy klasę języka C++, która zawiera prywatne dane elementu członkowskiego STL/CLR. Następnie deklarujemy metody publiczne, aby udzielić dostępu do prywatnych kolekcji klasy. Możemy to zrobić na dwa różne sposoby — jeden dla klientów C++ i jeden dla innych klientów platformy .NET.

### <a name="code"></a>Kod

```cpp
// StlClrClassLibrary.h
#pragma once

#include <cliext/deque>
#include <cliext/list>
#include <cliext/map>
#include <cliext/set>
#include <cliext/stack>
#include <cliext/vector>

using namespace System;
using namespace System::Collections::Generic;
using namespace cliext;

namespace StlClrClassLibrary {

    public ref class StlClrClass
    {
    public:
        StlClrClass();

        // These methods can be called by a C++ class
        // in another assembly to get access to the
        // private STL/CLR types defined below.
        deque<wchar_t>::generic_container ^GetDequeCpp();
        list<float>::generic_container ^GetListCpp();
        map<int, String ^>::generic_container ^GetMapCpp();
        set<double>::generic_container ^GetSetCpp();
        vector<int>::generic_container ^GetVectorCpp();

        // These methods can be called by a non-C++ class
        // in another assembly to get access to the
        // private STL/CLR types defined below.
        ICollection<wchar_t> ^GetDequeCs();
        ICollection<float> ^GetListCs();
        IDictionary<int, String ^> ^GetMapCs();
        ICollection<double> ^GetSetCs();
        ICollection<int> ^GetVectorCs();

    private:
        deque<wchar_t> ^aDeque;
        list<float> ^aList;
        map<int, String ^> ^aMap;
        set<double> ^aSet;
        vector<int> ^aVector;
    };
}
```

## <a name="example-2"></a>Przykład 2

### <a name="description"></a>Opis

W tym przykładzie implementujemy klasę zadeklarowaną w przykładzie 1. Aby klienci mogli korzystać z tej biblioteki klas, użyjemy **mt.exe** narzędzia manifestu do osadzenia pliku manifestu w bibliotece DLL. Aby uzyskać szczegółowe informacje, zobacz Komentarze do kodu.

Aby uzyskać więcej informacji na temat narzędzia manifestu i zestawów równoległych, zobacz [Kompilowanie aplikacji izolowanych C/C++ i zestawów równoległych](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md).

### <a name="code"></a>Kod

```cpp
// StlClrClassLibrary.cpp
// compile with: /clr /LD /link /manifest
// post-build command: (attrib -r StlClrClassLibrary.dll & mt /manifest StlClrClassLibrary.dll.manifest /outputresource:StlClrClassLibrary.dll;#2 & attrib +r StlClrClassLibrary.dll)

#include "StlClrClassLibrary.h"

namespace StlClrClassLibrary
{
    StlClrClass::StlClrClass()
    {
        aDeque = gcnew deque<wchar_t>();
        aDeque->push_back(L'a');
        aDeque->push_back(L'b');

        aList = gcnew list<float>();
        aList->push_back(3.14159f);
        aList->push_back(2.71828f);

        aMap = gcnew map<int, String ^>();
        aMap[0] = "Hello";
        aMap[1] = "World";

        aSet = gcnew set<double>();
        aSet->insert(3.14159);
        aSet->insert(2.71828);

        aVector = gcnew vector<int>();
        aVector->push_back(10);
        aVector->push_back(20);
    }

    deque<wchar_t>::generic_container ^StlClrClass::GetDequeCpp()
    {
        return aDeque;
    }

    list<float>::generic_container ^StlClrClass::GetListCpp()
    {
        return aList;
    }

    map<int, String ^>::generic_container ^StlClrClass::GetMapCpp()
    {
        return aMap;
    }

    set<double>::generic_container ^StlClrClass::GetSetCpp()
    {
        return aSet;
    }

    vector<int>::generic_container ^StlClrClass::GetVectorCpp()
    {
        return aVector;
    }

    ICollection<wchar_t> ^StlClrClass::GetDequeCs()
    {
        return aDeque;
    }

    ICollection<float> ^StlClrClass::GetListCs()
    {
        return aList;
    }

    IDictionary<int, String ^> ^StlClrClass::GetMapCs()
    {
        return aMap;
    }

    ICollection<double> ^StlClrClass::GetSetCs()
    {
        return aSet;
    }

    ICollection<int> ^StlClrClass::GetVectorCs()
    {
        return aVector;
    }
}
```

## <a name="example-3"></a>Przykład 3

### <a name="description"></a>Opis

W tym przykładzie tworzymy klienta języka C++, który używa biblioteki klas utworzonej w przykładach 1 i 2. Ten klient używa `generic_container` elementów typedef kontenerów STL/CLR do iteracji w kontenerach i wyświetlania ich zawartości.

### <a name="code"></a>Kod

```cpp
// CppConsoleApp.cpp
// compile with: /clr /FUStlClrClassLibrary.dll

#include <cliext/deque>
#include <cliext/list>
#include <cliext/map>
#include <cliext/set>
#include <cliext/vector>

using namespace System;
using namespace StlClrClassLibrary;
using namespace cliext;

int main(array<System::String ^> ^args)
{
    StlClrClass theClass;

    Console::WriteLine("cliext::deque contents:");
    deque<wchar_t>::generic_container ^aDeque = theClass.GetDequeCpp();
    for each (wchar_t wc in aDeque)
    {
        Console::WriteLine(wc);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::list contents:");
    list<float>::generic_container ^aList = theClass.GetListCpp();
    for each (float f in aList)
    {
        Console::WriteLine(f);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::map contents:");
    map<int, String ^>::generic_container ^aMap = theClass.GetMapCpp();
    for each (map<int, String ^>::value_type rp in aMap)
    {
        Console::WriteLine("{0} {1}", rp->first, rp->second);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::set contents:");
    set<double>::generic_container ^aSet = theClass.GetSetCpp();
    for each (double d in aSet)
    {
        Console::WriteLine(d);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::vector contents:");
    vector<int>::generic_container ^aVector = theClass.GetVectorCpp();
    for each (int i in aVector)
    {
        Console::WriteLine(i);
    }
    Console::WriteLine();

    return 0;
}
```

### <a name="output"></a>Dane wyjściowe

```Output
cliext::deque contents:
a
b

cliext::list contents:
3.14159
2.71828

cliext::map contents:
0 Hello
1 World

cliext::set contents:
2.71828
3.14159

cliext::vector contents:
10
20
```

## <a name="example-4"></a>Przykład 4

### <a name="description"></a>Opis

W tym przykładzie utworzysz klienta C#, który używa biblioteki klas utworzonej w przykładach 1 i 2. Ten klient używa <xref:System.Collections.Generic.ICollection%601> metod kontenerów STL/CLR do iteracji w kontenerach i wyświetlania ich zawartości.

### <a name="code"></a>Kod

```csharp
// CsConsoleApp.cs
// compile with: /r:Microsoft.VisualC.STLCLR.dll /r:StlClrClassLibrary.dll /r:System.dll

using System;
using System.Collections.Generic;
using StlClrClassLibrary;
using cliext;

namespace CsConsoleApp
{
    class Program
    {
        static int Main(string[] args)
        {
            StlClrClass theClass = new StlClrClass();

            Console.WriteLine("cliext::deque contents:");
            ICollection<char> iCollChar = theClass.GetDequeCs();
            foreach (char c in iCollChar)
            {
                Console.WriteLine(c);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::list contents:");
            ICollection<float> iCollFloat = theClass.GetListCs();
            foreach (float f in iCollFloat)
            {
                Console.WriteLine(f);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::map contents:");
            IDictionary<int, string> iDict = theClass.GetMapCs();
            foreach (KeyValuePair<int, string> kvp in iDict)
            {
                Console.WriteLine("{0} {1}", kvp.Key, kvp.Value);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::set contents:");
            ICollection<double> iCollDouble = theClass.GetSetCs();
            foreach (double d in iCollDouble)
            {
                Console.WriteLine(d);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::vector contents:");
            ICollection<int> iCollInt = theClass.GetVectorCs();
            foreach (int i in iCollInt)
            {
                Console.WriteLine(i);
            }
            Console.WriteLine();

            return 0;
        }
    }
}
```

### <a name="output"></a>Dane wyjściowe

```Output
cliext::deque contents:
a
b

cliext::list contents:
3.14159
2.71828

cliext::map contents:
0 Hello
1 World

cliext::set contents:
2.71828
3.14159

cliext::vector contents:
10
20
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja biblioteki STL/CLR](../dotnet/stl-clr-library-reference.md)
