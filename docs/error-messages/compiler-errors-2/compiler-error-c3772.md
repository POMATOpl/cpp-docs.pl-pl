---
description: 'Dowiedz się więcej o: błąd kompilatora C3772'
title: Błąd kompilatora C3772
ms.date: 11/04/2016
f1_keywords:
- C3772
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
ms.openlocfilehash: 679c5bc47e9b31ebf085dec63a46549a10484cac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340128"
---
# <a name="compiler-error-c3772"></a>Błąd kompilatora C3772

"name": nieprawidłowa deklaracja szablonu zaprzyjaźnionego

Nie można zadeklarować elementu zaprzyjaźnionego specjalizacji szablonu klasy. Nie można zadeklarować jawnej lub częściowej specjalizacji szablonu klasy, a w tej samej instrukcji deklaruje przyjaciela tej specjalizacji. Symbol zastępczy *name* identyfikuje nieprawidłową deklarację.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Nie deklaruj znajomości specjalizacji szablonu klasy.

- Jeśli jest to odpowiednie dla aplikacji, zadeklaruj znajomego szablonu klasy lub Zadeklaruj znajomego określonej częściowej lub jawnej specjalizacji.

## <a name="example"></a>Przykład

Poniższy przykład kodu nie powiedzie się, ponieważ deklaruje przyjaciela częściowej specjalizacji szablonu klasy.

```cpp
// c3772.cpp
// compile with: /c

// A class template.
    template<class T> class A {};

// A partial specialization of the class template.
    template<class T> class A<T*> {};

// An explicit specialization.
    template<> class A<char>;

class X {
// Invalid declaration of a friend of a partial specialization.
    template<class T> friend class A<T*>; // C3772

// Instead, if it is appropriate for your application, declare a
// friend of the class template. Consequently, all specializations
// of the class template are friends:
//    template<class T> friend class A;
// Or declare a friend of a particular partial specialization:
//    friend class A<int*>;
// Or declare a friend of a particular explicit specialization:
//    friend class A<char>;
};
```

## <a name="see-also"></a>Zobacz też

[Szablony](../../cpp/templates-cpp.md)<br/>
[Specjalizacja szablonu](../../cpp/template-specialization-cpp.md)
