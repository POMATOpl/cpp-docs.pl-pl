---
description: 'Dowiedz się więcej o: &lt; fstream — &gt; Typedefs'
title: '&lt;fstream — &gt; Typedefs'
ms.date: 11/04/2016
f1_keywords:
- fstream/std::filebuf
- fstream/std::fstream
- fstream/std::ifstream
- fstream/std::ofstream
- fstream/std::wfilebuf
- fstream/std::wfstream
- fstream/std::wifstream
- fstream/std::wofstream
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
ms.openlocfilehash: cf3a7d686bb1e6d6004aaf91fa50294225f0362d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232255"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream — &gt; Typedefs

[filebuf](#filebuf)\
[fstream —](#fstream)\
[ifstream](#ifstream)\
[ofstream](#ofstream)\
[wfilebuf](#wfilebuf)\
[wfstream](#wfstream)\
[wifstream](#wifstream)\
[wofstream](#wofstream)

## <a name="filebuf"></a><a name="filebuf"></a> filebuf

Typ `basic_filebuf` wyspecjalizowany dla **`char`** parametrów szablonu.

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_filebuf](../standard-library/basic-filebuf-class.md), wyspecjalizowany dla elementów typu **`char`** z cechami domyślnymi znaków.

## <a name="fstream"></a><a name="fstream"></a> fstream —

Typ `basic_fstream` wyspecjalizowany dla **`char`** parametrów szablonu.

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_fstream](../standard-library/basic-fstream-class.md), wyspecjalizowany dla elementów typu **`char`** z cechami domyślnymi znaków.

## <a name="ifstream"></a><a name="ifstream"></a> ifstream

Definiuje strumień, który ma być używany do odczytywania jednobajtowego danych znakowego z pliku. `ifstream` jest elementem TypeDef, który określa szablon klasy `basic_ifstream` dla **`char`** .

Istnieje również `wifstream` element typedef, który jest wyspecjalizowany `basic_ifstream` do odczytywania **`wchar_t`** podwójnych znaków. Aby uzyskać więcej informacji, zobacz [wifstream](../standard-library/fstream-typedefs.md#wifstream).

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_ifstream](../standard-library/basic-ifstream-class.md), wyspecjalizowany dla elementów typu char z domyślnymi cechami znaków. Przykładem jest

```cpp
using namespace std;

ifstream infile("existingtextfile.txt");

if (!infile.bad())
{
    // Dump the contents of the file to cout.
    cout << infile.rdbuf();infile.close();
}
```

## <a name="ofstream"></a><a name="ofstream"></a> ofstream

Typ `basic_ofstream` wyspecjalizowany dla **`char`** parametrów szablonu.

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_ofstream](../standard-library/basic-ofstream-class.md), wyspecjalizowany dla elementów typu **`char`** z cechami domyślnymi znaków.

## <a name="wfstream"></a><a name="wfstream"></a> wfstream

Typ `basic_fstream` wyspecjalizowany dla **`wchar_t`** parametrów szablonu.

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_fstream](../standard-library/basic-fstream-class.md), wyspecjalizowany dla elementów typu **`wchar_t`** z cechami domyślnymi znaków.

## <a name="wifstream"></a><a name="wifstream"></a> wifstream

Typ `basic_ifstream` wyspecjalizowany dla **`wchar_t`** parametrów szablonu.

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_ifstream](../standard-library/basic-ifstream-class.md), wyspecjalizowany dla elementów typu **`wchar_t`** z cechami domyślnymi znaków.

## <a name="wofstream"></a><a name="wofstream"></a> wofstream

Typ `basic_ofstream` wyspecjalizowany dla **`wchar_t`** parametrów szablonu.

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_ofstream](../standard-library/basic-ofstream-class.md), wyspecjalizowany dla elementów typu **`wchar_t`** z cechami domyślnymi znaków.

## <a name="wfilebuf"></a><a name="wfilebuf"></a> wfilebuf

Typ `basic_filebuf` wyspecjalizowany dla **`wchar_t`** parametrów szablonu.

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_filebuf](../standard-library/basic-filebuf-class.md), wyspecjalizowany dla elementów typu **`wchar_t`** z cechami domyślnymi znaków.

## <a name="see-also"></a>Zobacz też

[\<fstream>](../standard-library/fstream.md)
