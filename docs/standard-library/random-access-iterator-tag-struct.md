---
title: random_access_iterator_tag — struktura | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xutility/std::random_access_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- random_access_iterator_tag class
- random_access_iterator_tag struct
ms.assetid: 59f5b741-c5b4-459c-ad0a-3b67cddeea23
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfeea9ad12a7bec5225102abd3db92bbecf13f82
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="randomaccessiteratortag-struct"></a>random_access_iterator_tag — Struktura

Klasa, która zawiera typ zwracany dla **iterator_category** funkcja, która reprezentuje iteratora dostępie swobodnym.

## <a name="syntax"></a>Składnia

```cpp
struct random_access_iterator_tag    : public bidirectional_iterator_tag {};
```

## <a name="remarks"></a>Uwagi

Klasy tag kategorii są używane jako kompilacji znaczników dla algorytmu zaznaczenia. Funkcja szablonu musi znaleźć najbardziej określonej kategorii argumentu iteratora tak, aby najbardziej efektywny algorytm może użyć w czasie kompilacji. Dla każdego iteratora typu `Iterator`, `iterator_traits` <  `Iterator` >  **:: iterator_category** musi być zdefiniowany jako najbardziej konkretny tag kategorii, który określa zachowanie iteratora.

Typ jest taki sam jak **iterator** \< **Iter**> **:: iterator_category** podczas **Iter** opisuje obiekt, który może służyć jako iterator dostępie swobodnym.

## <a name="example"></a>Przykład

```cpp
// iterator_rait.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>
#include <list>

using namespace std;

int main( )
{
   vector<int> vi;
   vector<char> vc;
   list<char> lc;
   iterator_traits<vector<int>:: iterator>::iterator_category cati;
   iterator_traits<vector<char>:: iterator>::iterator_category catc;
   iterator_traits<list<char>:: iterator>::iterator_category catlc;

   // These are both random-access iterators
   cout << "The type of iterator for vector<int> is "
       << "identified by the tag:\n "
       << typeid ( cati ).name( ) << endl;
   cout << "The type of iterator for vector<char> is "
       << "identified by the tag:\n "
       << typeid ( catc ).name( ) << endl;
   if ( typeid ( cati ) == typeid( catc ) )
      cout << "The iterators are the same." << endl << endl;
   else
      cout << "The iterators are not the same." << endl << endl;

   // But the list iterator is bidirectinal, not random access
   cout << "The type of iterator for list<char> is "
       << "identified by the tag:\n "
       << typeid (catlc).name( ) << endl;

   // cout << ( typeid ( vi.begin( ) ) == typeid( vc.begin( ) ) ) << endl;
   if ( typeid ( vi.begin( ) ) == typeid( vc.begin( ) ) )
      cout << "The iterators are the same." << endl;
   else
      cout << "The iterators are not the same." << endl;
   // A random-access iterator is a bidirectional iterator.
   cout << ( void* ) dynamic_cast< iterator_traits<list<char>:: iterator>
          ::iterator_category* > ( &catc ) << endl;
}
```

## <a name="sample-output"></a>Przykładowe dane wyjściowe

Następujące dane wyjściowe dotyczy x86.

```Output
The type of iterator for vector<int> is identified by the tag:
    struct std::random_access_iterator_tag
The type of iterator for vector<char> is identified by the tag:
    struct std::random_access_iterator_tag
The iterators are the same.

The type of iterator for list<char> is identified by the tag:
    struct std::bidirectional_iterator_tag
The iterators are not the same.
0012FF3B
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<iteratora >

**Namespace:** Standard

## <a name="see-also"></a>Zobacz także

[bidirectional_iterator_tag, struktura](../standard-library/bidirectional-iterator-tag-struct.md)<br/>
[Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Dokumentacja standardowej biblioteki C++](../standard-library/cpp-standard-library-reference.md)<br/>
