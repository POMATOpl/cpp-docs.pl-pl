---
description: 'Dowiedz się więcej o: błąd kompilatora C2243'
title: Błąd kompilatora C2243
ms.date: 11/04/2016
f1_keywords:
- C2243
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
ms.openlocfilehash: 48947ee39e61b2db1a64023f730b89d8be8d1907
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302196"
---
# <a name="compiler-error-c2243"></a>Błąd kompilatora C2243

Konwersja "typ konwersji" z "type1" na "type2" istnieje, ale jest niedostępna

Ochrona dostępu ( **`protected`** lub **`private`** ) uniemożliwiła konwersję ze wskaźnika do klasy pochodnej na wskaźnik do klasy bazowej.

Poniższy przykład generuje C2243:

```cpp
// C2243.cpp
// compile with: /c
class B {};
class D : private B {};
class E : public B {};

D d;
B *p = &d;   // C2243

E e;
B *p2 = &e;
```

Klasy bazowe z **`protected`** lub **`private`** dostępu są niedostępne dla klientów klasy pochodnej. Te poziomy kontroli dostępu są używane do wskazywania, że klasa podstawowa jest szczegółami implementacji, które powinny być niewidoczne dla klientów. Użyj publicznej metody tworzenia, jeśli chcesz, aby klienci klasy pochodnej mieli dostęp do niejawnej konwersji wskaźnika klasy pochodnej na wskaźnik do klasy bazowej.
