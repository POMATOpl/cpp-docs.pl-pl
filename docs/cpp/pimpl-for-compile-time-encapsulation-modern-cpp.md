---
description: Dowiedz się więcej o programie Mechanizm pimpl hermetyzacji for Compile-Time Encapsulation (nowoczesny C++)
title: Mechanizm pimpl hermetyzacji w czasie kompilacji (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: 95d1ca4f377cc911e862885e86f846d8536d3b1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145889"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Mechanizm pimpl hermetyzacji w czasie kompilacji (Modern C++)

*Mechanizm pimpl hermetyzacji idiom* jest nowoczesnym techniką języka C++ do ukrycia implementacji, minimalizowania sprzęgu i oddzielenia interfejsów. Mechanizm pimpl hermetyzacji jest krótkie dla "wskaźnika do implementacji". Użytkownik może już znać koncepcję, ale znać inne nazwy, takie jak Cheshire Cat lub kompilator idiom.

## <a name="why-use-pimpl"></a>Dlaczego warto używać Mechanizm pimpl hermetyzacji?

Oto, jak Mechanizm pimpl hermetyzacji idiom może ulepszyć cykl programowania oprogramowania:

- Minimalizacja zależności kompilacji.

- Rozdzielenie interfejsu i implementacji.

- Przenośność.

## <a name="pimpl-header"></a>Mechanizm pimpl hermetyzacji — nagłówek

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

Mechanizm pimpl hermetyzacji idiom pozwala uniknąć ponownego kompilowania kaskad i układów obiektów kruchy. Jest to dobrze dostosowane do popularnych typów (przechodnie).

## <a name="pimpl-implementation"></a>Implementacja Mechanizm pimpl hermetyzacji

Zdefiniuj `impl` klasę w pliku CPP.

```cpp
// my_class.cpp
class my_class::impl {  // defined privately here
  // ... all private data and functions: all of these
  //     can now change without recompiling callers ...
};
my_class::my_class(): pimpl( new impl )
{
  // ... set impl values ...
}
```

## <a name="best-practices"></a>Najlepsze rozwiązania

Weź pod uwagę, czy dodać obsługę niezgłaszanej specjalizacji wymiany.

## <a name="see-also"></a>Zobacz też

[Witamy ponownie w języku C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Dokumentacja języka C++](../cpp/cpp-language-reference.md)<br/>
[Standardowa biblioteka języka C++](../standard-library/cpp-standard-library-reference.md)
