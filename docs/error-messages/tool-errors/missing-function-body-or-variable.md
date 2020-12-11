---
description: 'Dowiedz się więcej o: Brakująca treść funkcji lub zmienna'
title: Brakująca treść funkcji lub zmienna
ms.date: 11/04/2016
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
ms.openlocfilehash: 6a4349c380fc0f573adc8e372f9e4d2fc3f83873
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155166"
---
# <a name="missing-function-body-or-variable"></a>Brakująca treść funkcji lub zmienna

Za pomocą tylko prototypu funkcji kompilator może kontynuować bez błędu, ale konsolidator nie może rozpoznać wywołania do adresu, ponieważ nie istnieje kod funkcji ani zarezerwowane miejsce na zmienne. Ten błąd nie zostanie wyświetlony do momentu utworzenia wywołania funkcji, którą konsolidator musi rozpoznać.

## <a name="example-call-to-an-undefined-function"></a>Przykład: wywołanie funkcji undefined

Wywołanie funkcji w głównym spowoduje wystąpienie LNK2019, ponieważ prototyp umożliwia kompilatorowi określenie, że funkcja już istnieje.  Konsolidator stwierdzi, że nie.

```cpp
// LNK2019_MFBV.cpp
// LNK2019 expected
void DoSomething(void);
int main() {
   DoSomething();
}
```

## <a name="example-call-to-an-implemented-function"></a>Przykład: wywołanie zaimplementowanej funkcji

W języku C++ upewnij się, że dołączysz implementację określonej funkcji dla klasy, a nie tylko prototyp w definicji klasy. Jeśli definiujesz klasę poza plikiem nagłówkowym, pamiętaj o uwzględnieniu nazwy klasy przed funkcją ( `Classname::memberfunction` ).

```cpp
// LNK2019_MFBV_2.cpp
// LNK2019 expected
struct A {
   static void Test();
};

// Should be void A::Test() {}
void Test() {}

int main() {
   A AObject;
   AObject.Test();
}
```

## <a name="see-also"></a>Zobacz też

[LNK2019 błędu narzędzi konsolidatora](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
