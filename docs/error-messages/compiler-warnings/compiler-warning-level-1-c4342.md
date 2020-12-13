---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4342'
title: Ostrzeżenie kompilatora (poziom 1) C4342
ms.date: 11/04/2016
f1_keywords:
- C4342
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
ms.openlocfilehash: f08cf24b0fe429e8b788a20fbcb05d2a8cd8b1d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340023"
---
# <a name="compiler-warning-level-1-c4342"></a>Ostrzeżenie kompilatora (poziom 1) C4342

zmiana zachowania: wywołano *funkcję "Function*", ale operator składowej został wywołany w poprzednich wersjach

W wersjach Visual C++ przed Visual Studio 2002, element członkowski został wywołany, ale to zachowanie zostało zmienione i kompilator znalazł teraz najlepsze dopasowanie w zakresie przestrzeni nazw.

Jeśli zostanie znaleziony operator elementu członkowskiego, kompilator nie uwzględni wcześniej operatorów zakresu przestrzeni nazw. W przypadku lepszego dopasowania w zakresie przestrzeni nazw, bieżący kompilator prawidłowo wywołuje go, podczas gdy poprzedni kompilator nie uważa go.

To ostrzeżenie powinno być wyłączone po pomyślnym przejściu kodu do bieżącej wersji.  Kompilator może dać fałszywe pozytywne wartości, generując to ostrzeżenie dla kodu, w którym nie ma żadnych zmian w zachowaniu.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji, zobacz [ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Poniższy przykład generuje C4342:

```cpp
// C4342.cpp
// compile with: /EHsc /W1
#include <fstream>
#pragma warning(default: 4342)
using namespace std;
struct X : public ofstream {
   X();
};

X::X() {
   open( "ofs_bug_ev.txt." );
   if ( is_open() ) {
      *this << "Text" << "<-should be text" << endl;   // C4342
      *this << ' ' << "<-should be space symbol" << endl;   // C4342
   }
}

int main() {
   X b;
   b << "Text" << "<-should be text" << endl;
   b << ' ' << "<-should be space symbol" << endl;
}
```
