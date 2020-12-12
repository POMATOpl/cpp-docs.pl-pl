---
description: Dowiedz się więcej na temat klasy nested_exception
title: Klasa nested_exception
ms.date: 11/04/2016
f1_keywords:
- exception/std::nested_exception
helpviewer_keywords:
- nested_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: fd2a0d5b62eb0ec9ae1e70233984fe7457127414
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338206"
---
# <a name="nested_exception-class"></a>Klasa nested_exception

Klasa opisuje wyjątek do użycia z wielokrotnym dziedziczeniem. Przechwytuje aktualnie obsłużony wyjątek i zapisuje go do późniejszego użycia.

## <a name="syntax"></a>Składnia

```cpp
class nested_exception {
    public:
        nested_exception();
        nested_exception(const nested_exception&) = default;
        virtual ~nested_exception() = default; // access functions
};
```

## <a name="members"></a>Elementy członkowskie

### <a name="operators"></a>Operatory

|Nazwa|Opis|
|-|-|
|[operator =](#op_as)|Operator przypisania.|

### <a name="functions"></a>Funkcje

|Nazwa|Opis|
|-|-|
|[rethrow_nested](#rethrow_nested)|Zgłasza wyjątek przechowywany.|
|[nested_ptr](#nested_ptr)|Zwraca przechowywany wyjątek.|

### <a name="operator"></a><a name="op_as"></a> operator =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a><a name="nested_ptr"></a> nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>Wartość zwracana

Przechowywany wyjątek przechwytywany przez ten `nested_exception` obiekt.

### <a name="rethrow_nested"></a><a name="rethrow_nested"></a> rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Uwagi

Jeśli `nested_ptr()` zwraca wskaźnik o wartości null, wywołuje funkcję `std::terminate()` . W przeciwnym razie zgłasza przechowywany wyjątek przechwytywany przez **`*this`** .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<exception>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Klasa wyjątku](../standard-library/exception-class.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
