---
description: 'Dowiedz się więcej na temat: przestarzałe (C++)'
title: przestarzałe (C++)
ms.date: 03/28/2017
f1_keywords:
- deprecated_cpp
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
ms.openlocfilehash: cd7bc3acbe6a61e87a1766025bcc174268190c48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339426"
---
# <a name="deprecated-c"></a>przestarzałe (C++)

W tym temacie opisano przestarzałą deklarację declspec zainstalowaną przez firmę Microsoft. Aby uzyskać informacje na temat atrybutu C++ 14 `[[deprecated]]` i wskazówki dotyczące sytuacji, w których należy używać tego atrybutu w porównaniu z declspec lub pragma specyficzna dla firmy Microsoft, zobacz [atrybuty standardowe języka c++](attributes.md).

Zgodnie z wyjątkami wymienionymi poniżej, **`deprecated`** Deklaracja oferuje te same funkcje co [przestarzała](../preprocessor/deprecated-c-cpp.md) dyrektywa pragma:

- **`deprecated`** Deklaracja pozwala określić określone formy przeciążeń funkcji jako przestarzałe, natomiast formularz pragma dotyczy wszystkich przeciążonych formularzy nazwy funkcji.

- **`deprecated`** Deklaracja pozwala określić komunikat, który będzie wyświetlany w czasie kompilacji. Tekst komunikatu może pochodzić z makra.

- Makra można oznaczyć tylko jako przestarzałe przy użyciu **`deprecated`** dyrektywy pragma.

Jeśli kompilator napotyka użycie przestarzałego identyfikatora lub [`[[deprecated]]`](attributes.md) atrybutu standardowego, zostanie wygenerowane ostrzeżenie [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) .

## <a name="examples"></a>Przykłady

Poniższy przykład pokazuje, jak oznaczyć funkcje jako przestarzałe i jak określić komunikat, który będzie wyświetlany w czasie kompilacji, gdy zostanie użyta funkcja przestarzałe.

```cpp
// deprecated.cpp
// compile with: /W3
#define MY_TEXT "function is deprecated"
void func1(void) {}
__declspec(deprecated) void func1(int) {}
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}
__declspec(deprecated(MY_TEXT)) void func3(int) {}

int main() {
   func1();
   func1(1);   // C4996
   func2(1);   // C4996
   func3(1);   // C4996
}
```

Poniższy przykład pokazuje, jak oznaczyć klasy jako przestarzałe i jak określić komunikat, który będzie wyświetlany w czasie kompilacji, gdy przestarzała Klasa jest używana.

```cpp
// deprecate_class.cpp
// compile with: /W3
struct __declspec(deprecated) X {
   void f(){}
};

struct __declspec(deprecated("** X2 is deprecated **")) X2 {
   void f(){}
};

int main() {
   X x;   // C4996
   X2 x2;   // C4996
}
```

## <a name="see-also"></a>Zobacz też

[__declspec](../cpp/declspec.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)
