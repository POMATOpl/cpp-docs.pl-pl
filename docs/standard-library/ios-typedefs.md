---
title: '`<ios>`, definicje typów'
description: Opisuje definicje typów języka C++ Standard (STL) `<ios>` , które obsługują `ios` klasę z starej `iostream` biblioteki.
ms.date: 11/06/2020
f1_keywords:
- iosfwd/std::ios
- iosfwd/std::streamoff
- iosfwd/std::streampos
- iosfwd/std::streamsize
- iosfwd/std::wios
- iosfwd/std::wstreampos
ms.openlocfilehash: b9dbed64c88a00f5ca065e23c4af2f3922634ece
ms.sourcegitcommit: b38485bb3a9d479e0c5d64ffc3d841fa2c2b366f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441271"
---
# <a name="ios-typedefs"></a>`<ios>`, definicje typów

## `ios`

Obsługuje `ios` klasę ze starej `iostream` biblioteki.

```cpp
typedef basic_ios<char, char_traits<char>> ios;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [`basic_ios`](../standard-library/basic-ios-class.md) , wyspecjalizowanym dla elementów typu **`char`** z cechami domyślnymi znaków.

## `streamoff`

Obsługuje operacje wewnętrzne.

```cpp
#ifdef _WIN64
    typedef __int64 streamoff;
#else
    typedef long streamoff;
#endif
```

### <a name="remarks"></a>Uwagi

Typ to liczba całkowita ze znakiem. Opisuje obiekt, który może przechowywać przesunięcie bajtów w operacjach umieszczania w strumieniu. Jego reprezentacja ma co najmniej 32 bitów wartości. Nie musi być wystarczająco duże, aby reprezentować dowolną pozycję bajtową w strumieniu. Wartość `streamoff(-1)` zwykle wskazuje błędne przesunięcie.

## `streampos`

Przechowuje bieżącą pozycję wskaźnika buforu lub wskaźnika pliku.

```cpp
typedef fpos<mbstate_t> streampos;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla [`fpos`](../standard-library/fpos-class.md) <  `mbstate_t`>.

### <a name="example"></a>Przykład

```cpp
// ios_streampos.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;

   ofstream x( "iostream.txt" );
   x << "testing";
   streampos y = x.tellp( );
   cout << streamoff( y ) << '\n';
}
```

```Output
7
```

## `streamsize`

Określa rozmiar strumienia.

```cpp
#ifdef _WIN64
    typedef __int64 streamsize;
#else
    typedef int streamsize;
#endif
```

### <a name="remarks"></a>Uwagi

Typ to liczba całkowita ze znakiem, która opisuje obiekt, który może przechowywać liczbę elementów występujących w różnych operacjach strumienia. Jego reprezentacja ma co najmniej 16 bitów. Nie musi być wystarczająco duże, aby reprezentować dowolną pozycję bajtową w strumieniu.

### <a name="example"></a>Przykład

Po skompilowaniu i uruchomieniu następującego programu Przyjrzyj się plikowi, `test.txt` Aby zobaczyć efekt ustawienia `streamsize` .

```cpp
// ios_streamsize.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   char a[16] = "any such text";
   ofstream x( "test.txt" );
   streamsize y = 6;
   x.write( a, y );
}
```

## `wios`

Obsługuje `wios` klasę ze starej `iostream` biblioteki.

```cpp
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [`basic_ios`](../standard-library/basic-ios-class.md) , wyspecjalizowanym dla elementów typu **`wchar_t`** z cechami domyślnymi znaków.

## `wstreampos`

Przechowuje bieżącą pozycję wskaźnika buforu lub wskaźnika pliku.

```cpp
typedef fpos<mbstate_t> wstreampos;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla [`fpos`](../standard-library/fpos-class.md) <  `mbstate_t`>.

### <a name="example"></a>Przykład

```cpp
// ios_wstreampos.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   wofstream xw( "wiostream.txt" );
   xw << L"testing";
   wstreampos y = xw.tellp( );
   cout << streamoff( y ) << '\n';
}
```

```Output
7
```
