---
title: Narzędzie (STL/CLR) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/utility>
- cliext::pair
- cliext::pair::pair
- cliext::pair::first
- cliext::pair::first_type
- cliext::pair::second
- cliext::pair::second_type
- cliext::pair::swap
- cliext::make_pair
- cliext::pair::operator=
- cliext::pair::operator==
- cliext::pair::operator>=
- cliext::pair::operator>
- cliext::pair::operator!=
- cliext::pair::operator<=
- cliext::pair::operator<
dev_langs:
- C++
helpviewer_keywords:
- <utility> header [STL/CLR]
- utility header [STL/CLR]
- <cliext/utility> header [STL/CLR]
- first member [STL/CLR]
- first_type member [STL/CLR]
- second member [STL/CLR]
- second_type member [STL/CLR]
- swap member [STL/CLR]
- make_pair function [STL/CLR]
- pair class [STL/CLR]
- pair member [STL/CLR]
- operator== member [STL/CLR]
- operator= member [STL/CLR]
- operator>= member [STL/CLR]
- operator> member [STL/CLR]
- operator!= member [STL/CLR]
- operator<= member [STL/CLR]
- operator< member [STL/CLR]
ms.assetid: fb48cb75-d5ef-47ce-b526-bf60dc86c552
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e1150fb6d3df325fd9d5d9b4180318fa029102c3
ms.sourcegitcommit: bad2441d1930275ff506d44759d283d94cccd1c0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2018
ms.locfileid: "39375919"
---
# <a name="utility-stlclr"></a>utility (STL/CLR)
Dołącz nagłówek STL/CLR `<cliext/utility>` Aby zdefiniować klasę szablonu `pair` i kilka funkcji szablonów pomocniczych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
#include <utility>  
```

## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<cliext — / Narzędzia >  
  
 **Namespace:** cliext —  
  
## <a name="declarations"></a>Deklaracje  
  
|Class|Opis|  
|-----------|-----------------|  
|[pair (STL/CLR)](#pair)|Otoczenie pary elementów.|  
  
|Operator|Opis|  
|--------------|-----------------|  
|[operator== (pair) (STL/CLR)](#op_eq)|Porównanie równego pary.|  
|[operator!= (pair) (STL/CLR)](#op_neq)|Para równa porównania.|  
|[operator< (pair) (STL/CLR)](#op_lt)|Para mniejszą niż porównania.|  
|[operator\<= (parę) (STL/CLR)](#op_lteq)|Sparuj mniejsza lub równa porównania.|  
|[operator> (pair) (STL/CLR)](#op_gt)|Para jest większa niż porównania.|  
|[operator>= (pair) (STL/CLR)](#op_gteq)|Para większa niż lub równe porównania.|  
  
|Funkcja|Opis|  
|--------------|-----------------|  
|[make_pair (STL/CLR)](#make_pair)|Wprowadź pary z pary wartości.|  

## <a name="members"></a>Elementy członkowskie

##<a name="pair"></a> pary (STL/CLR)
Klasa szablonu opisuje obiekt, który opakowuje pary wartości.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### <a name="parameters"></a>Parametry  
 *Wartość1*  
 Typ pierwszego zakodowana wartość.  
  
 *Wartość2*  
 Typ drugiego zakodowana wartość.  
  
## <a name="members"></a>Elementy członkowskie  
  
|Definicja typu|Opis|  
|---------------------|-----------------|  
|[pair::first_type (STL/CLR)](#first_type)|Typ pierwszego zakodowana wartość.|  
|[pair::second_type (STL/CLR)](#second_type)|Typ drugiego zakodowana wartość.|  
  
|Element członkowski obiektu|Opis|  
|-------------------|-----------------|  
|[pair::first (STL/CLR)](#first)|Pierwszy przechowywaną wartość.|  
|[pair::second (STL/CLR)](#second)|Drugi przechowywaną wartość.|  
  
|Funkcja elementów członkowskich|Opis|  
|---------------------|-----------------|  
|[pair::pair (STL/CLR)](#pair_pair)|Tworzy obiekt pary.|  
|[pair::swap (STL/CLR)](#swap)|Zamienia zawartości dwóch par.|  
  
|Operator|Opis|  
|--------------|-----------------|  
|[pair::operator= (STL/CLR)](#op_as)|Zastępuje przechowywane pary wartości.|  
  
## <a name="remarks"></a>Uwagi  
 Obiekt przechowuje pary wartości. Użyjesz tej klasy szablonu do łączenia dwóch wartości w pojedynczy obiekt. Ponadto obiektu `cliext::pair` (opisanych poniżej) magazynów tylko zarządzane typy; aby przechowywać pary niezarządzanych użyć typów `std::pair`, zadeklarowanych w `<utility>`.  


## <a name="first"></a> Pair::First (STL/CLR)
Pierwsza wartość opakowana.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
Value1 first;  
```  
  
### <a name="remarks"></a>Uwagi  
 Obiekt przechowuje pierwszą zakodowana wartość.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_first.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
```  
  
```Output  
[x, 3]  
```  

## <a name="first_type"></a> Pair::first_type (STL/CLR)
Typ pierwszego zakodowana wartość.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
typedef Value1 first_type;  
```  
  
### <a name="remarks"></a>Uwagi  
 Typ jest synonimem dla parametru szablonu *wartość1*.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_first_type.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }   
```  
  
```Output  
[x, 3]  
```  

## <a name="op_as"></a> Pair::operator = (STL/CLR)
Zastępuje przechowywane pary wartości.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametry  
 *right*  
 Para do skopiowania.  
  
### <a name="remarks"></a>Uwagi  
 Kopiuje operator składowej *prawo* do obiektu, następnie zwraca `*this`. Umożliwia ona Zastąp kopii przechowywanej pary wartości w parze przechowywanej wartości *prawo*.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_operator_as.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
// assign to a new pair   
    cliext::pair<wchar_t, int> c2;   
    c2 = c1;   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
    return (0);   
    }   
```  
  
```Output  
[x, 3]  
[x, 3]  
```  

## <a name="pair_pair"></a> Pair::Pair (STL/CLR)
Tworzy obiekt pary.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
pair();  
pair(pair<Coll>% right);  
pair(pair<Coll>^ right);  
pair(Value1 val1, Value2 val2);  
```  
  
#### <a name="parameters"></a>Parametry  
 *right*  
 Para do przechowywania.  
  
 *val1*  
 Pierwsza wartość do przechowywania.  
  
 *Val2*  
 Druga wartość do przechowywania.  
  
### <a name="remarks"></a>Uwagi  
 Konstruktor:  
  
 `pair();`  
  
 Inicjuje przechowywanych pary wartości domyślne.  
  
 Konstruktor:  
  
 `pair(pair<Value1, Value2>% right);`  
  
 Inicjuje przechowywanych twórz pary za pomocą `right.` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) i `right.` [pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md).  
  
 `pair(pair<Value1, Value2>^ right);`  
  
 Inicjuje przechowywanych twórz pary za pomocą `right->` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) i `right>` [pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md).  
  
 Konstruktor:  
  
 `pair(Value1 val1, Value2 val2);`  
  
 Inicjuje przechowywanych twórz pary za pomocą z *val1* i *val2*.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_construct.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
// construct an empty container   
    cliext::pair<wchar_t, int> c1;   
    System::Console::WriteLine("[{0}, {1}]",   
        c1.first == L'\0' ? "\\0" : "??", c1.second);   
  
// construct with a pair of values   
    cliext::pair<wchar_t, int> c2(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
// construct by copying another pair   
    cliext::pair<wchar_t, int> c3(c2);   
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);   
  
// construct by copying a pair handle   
    cliext::pair<wchar_t, int> c4(%c3);   
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);   
  
    return (0);   
    }   
```  
  
```Output  
[\0, 0]  
[x, 3]  
[x, 3]  
[x, 3]  
```  

## <a name="second"></a> Pair::Second (STL/CLR)
Drugi opakowane wartości.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
Value2 second;  
```  
  
### <a name="remarks"></a>Uwagi  
 Obiekt przechowuje drugi zakodowana wartość.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_second.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
```  
  
```Output  
[x, 3]  
```  

## <a name="second_type"></a> Pair::second_type (STL/CLR)
Typ drugiego zakodowana wartość.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
typedef Value2 second_type;  
```  
  
### <a name="remarks"></a>Uwagi  
 Typ jest synonimem dla parametru szablonu *wartość2*.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_second_type.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }   
```  
  
```Output  
[x, 3]  
```    

## <a name="swap"></a> Pair::swap (STL/CLR)
Zamienia zawartości dwóch par.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
void swap(pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametry  
 *right*  
 Para do wymiany zawartości z.  
  
### <a name="remarks"></a>Uwagi  
 Funkcja elementu członkowskiego zamienia przechowywanych pary wartości z zakresu od `*this` i *prawo*.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_swap.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> d2(5, L'x');   
    Mycoll c2(%d2);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }   
```  
  
```Output  
a b c  
x x x x x  
x x x x x  
a b c  
```  

## <a name="make_pair"></a> make_pair (STL/CLR)
Wprowadź `pair` z pary wartości.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
template<typename Value1,  
    typename Value2>  
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);  
```  
  
#### <a name="parameters"></a>Parametry  
 *Wartość1*  
 Typ pierwszego zakodowana wartość.  
  
 *Wartość2*  
 Typ drugiego zakodowana wartość.  
  
 *pierwszy*  
 Pierwsza wartość do opakowania.  
  
 *Sekundy*  
 Druga wartość do zakodowania.  
  
### <a name="remarks"></a>Uwagi  
 Funkcja szablonu zwraca `pair<Value1, Value2>(first, second)`. Służy do konstruowania `pair<Value1, Value2>` obiekt z parą wartości.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_make_pair.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    c1 = cliext::make_pair(L'y', 4);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    return (0);   
    }  
```  
  
```Output  
[x, 3]  
[y, 4]  
```  

## <a name="op_neq"></a> Operator! = (parę) (STL/CLR)
Para równa porównania.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
template<typename Value1,  
    typename Value2>  
    bool operator!=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametry  
 *left*  
 Po lewej stronie para do porównania.  
  
 *right*  
 Para prawo do porównania.  
  
### <a name="remarks"></a>Uwagi  
 Funkcja operator zwraca `!(left == right)`. Można go używać do testowania czy *po lewej stronie* nie jest taka sama jak określona *prawo* kiedy dwie pary są w porównaniu element po elemencie.  
  
### <a name="example"></a>Przykład  
  
```cpp
// cliext_pair_operator_ne.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] != [x 3] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[x 3] != [x 4] is {0}",   
        c1 != c2);   
    return (0);   
    }   
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] != [x 3] is False  
[x 3] != [x 4] is True  
```  
  
## <a name="op_lt"></a> operator&lt; (parę) (STL/CLR)
Para mniejszą niż porównania.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
template<typename Value1,  
    typename Value2>  
    bool operator<(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametry  
 *left*  
 Po lewej stronie para do porównania.  
  
 *right*  
 Para prawo do porównania.  
  
### <a name="remarks"></a>Uwagi  
 Funkcja operator zwraca `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second`. Można go używać do testowania czy *po lewej stronie* są porządkowane przed *prawo* kiedy dwie pary są w porównaniu element po elemencie.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_operator_lt.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] < [x 3] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[x 3] < [x 4] is {0}",   
        c1 < c2);   
    return (0);   
    }   
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] < [x 3] is False  
[x 3] < [x 4] is True  
```  

## <a name="op_lteq"></a> operator&lt;= (parę) (STL/CLR)
Sparuj mniejsza lub równa porównania.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
template<typename Value1,  
    typename Value2>  
    bool operator<=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametry  
 *left*  
 Po lewej stronie para do porównania.  
  
 *right*  
 Para prawo do porównania.  
  
### <a name="remarks"></a>Uwagi  
 Funkcja operator zwraca `!(right < left)`. Można go używać do testowania czy *po lewej stronie* nie są porządkowane po *prawo* kiedy dwie pary są w porównaniu element po elemencie.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_operator_le.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] <= [x 3] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",   
        c2 <= c1);   
    return (0);   
    }   
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] <= [x 3] is True  
[x 4] <= [x 3] is False  
```  
  
## <a name="op_eq"></a> Operator == (parę) (STL/CLR)
Porównanie równego pary.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
template<typename Value1,  
    typename Value2>  
    bool operator==(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametry  
 *left*  
 Po lewej stronie para do porównania.  
  
 *right*  
 Para prawo do porównania.  
  
### <a name="remarks"></a>Uwagi  
 Funkcja operator zwraca `left.first ==` `right.first &&` `left.second ==` `right.second`. Można go używać do testowania czy *po lewej stronie* jest taka sama jak określona *prawo* kiedy dwie pary są w porównaniu element po elemencie.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_operator_eq.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] == [x 3] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[x 3] == [x 4] is {0}",   
        c1 == c2);   
    return (0);   
    }   
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] == [x 3] is True  
[x 3] == [x 4] is False  
```  

## <a name="op_gt"></a> operator&gt; (parę) (STL/CLR)
Para jest większa niż porównania.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
template<typename Value1,  
    typename Value2>  
    bool operator>(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametry  
 *left*  
 Po lewej stronie para do porównania.  
  
 *right*  
 Para prawo do porównania.  
  
### <a name="remarks"></a>Uwagi  
 Funkcja operator zwraca `right` `<` `left`. Można go używać do testowania czy *po lewej stronie* są porządkowane po *prawo* kiedy dwie pary są w porównaniu element po elemencie.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_operator_gt.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] > [x 3] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[x 4] > [x 3] is {0}",   
        c2 > c1);   
    return (0);   
    }   
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] > [x 3] is False  
[x 4] > [x 3] is True  
```  

## <a name="op_gteq"></a> operator&gt;= (parę) (STL/CLR)
Para większa niż lub równe porównania.  
  
### <a name="syntax"></a>Składnia  
  
```cpp  
template<typename Value1,  
    typename Value2>  
    bool operator>=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametry  
 *left*  
 Po lewej stronie para do porównania.  
  
 *right*  
 Para prawo do porównania.  
  
### <a name="remarks"></a>Uwagi  
 Funkcja operator zwraca `!(left < right)`. Można go używać do testowania czy *po lewej stronie* nie był zamówiony przed *prawo* kiedy dwie pary są w porównaniu element po elemencie.  
  
### <a name="example"></a>Przykład  
  
```cpp  
// cliext_pair_operator_ge.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] >= [x 3] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",   
        c1 >= c2);   
    return (0);   
    }   
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] >= [x 3] is True  
[x 3] >= [x 4] is False  
``` 