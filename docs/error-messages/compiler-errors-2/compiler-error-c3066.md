---
title: Błąd kompilatora C3066 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3066
dev_langs:
- C++
helpviewer_keywords:
- C3066
ms.assetid: 226f6de5-c4c5-41e2-b31a-2e30a37fbbeb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35600fae9a689b32cca9c327645a0e0c1bb91a25
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084617"
---
# <a name="compiler-error-c3066"></a>Błąd kompilatora C3066

istnieje wiele sposobów obiektu tego typu można wywołać z tymi argumentami

Kompilator wykrył wywołanie niejednoznaczną funkcję obejmujące surogaty.

Poniższy przykład spowoduje wygenerowanie C3066:

```
// C3066.cpp
template <class T, class U> void func(T*, U*){}

typedef void (*PF)(const int*, const char*);
typedef void (*PF1)(const int*, volatile char*);

struct A {
   operator PF() const {
      return func;
   }

   operator PF1() {
      return func;
   }

   operator PF1() const  {
      return func;
   }

};

int main() {
   A a;
   int i;
   char c;

   a(&i, &c);   // C3066
   a(&i, (const char *) &c);   // OK
}
```

## <a name="copy-list-initialization"></a>Copy-list-initialization

W programie Visual Studio 2015 kompilator błędnie traktowane listy Inicjalizacja kopiowania na w taki sam sposób, jak regularne Inicjowanie kopiowania; uznaje się jedynie konwertowanie konstruktory przeciążeń z późnym wiązaniem. W poniższym przykładzie Visual Studio 2015 wybiera MyInt(23), ale Visual Studio 2017 niepoprawnie zgłasza błąd.

```
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyList {
       explicit MyStore(int initialCapacity);
};

struct MyInt {
       MyInt(int i);
};

struct Printer {
       void operator()(MyStore const& s);
       void operator()(MyInt const& i);
};

void f() {
       Printer p;
       p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```