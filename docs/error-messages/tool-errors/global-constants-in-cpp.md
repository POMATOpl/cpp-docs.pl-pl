---
description: 'Dowiedz się więcej o: globalnych stałych w języku C++'
title: Stałe globalne w C++
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: 8e960e7e10942fc231fcdeafef6e8d755694c460
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261661"
---
# <a name="global-constants-in-c"></a>Stałe globalne w C++

Globalne stałe języka C++ mają połączenie statyczne. Jest to inne niż C. Jeśli spróbujesz użyć stałej globalnej w języku C++ w wielu plikach, wystąpi błąd zewnętrzny. Kompilator optymalizuje stałe globalne, pozostawiając bez miejsca zarezerwowane dla zmiennej.

Jednym ze sposobów na rozwiązanie tego błędu jest dołączenie do pliku nagłówkowego inicjujących inicjalizacje i uwzględnienie tego nagłówka w plikach CPP, podobnie jak w przypadku prototypu funkcji. Kolejną możliwością jest, aby zmienna nie stała i używała stałego odwołania podczas jego oceniania.

Poniższy przykład generuje C2019:

```cpp
// global_constants.cpp
// LNK2019 expected
void test(void);
const int lnktest1 = 0;

int main() {
   test();
}
```

A następnie

```cpp
// global_constants_2.cpp
// compile with: global_constants.cpp
extern int lnktest1;

void test() {
  int i = lnktest1;   // LNK2019
}
```

## <a name="see-also"></a>Zobacz też

[LNK2019 błędu narzędzi konsolidatora](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
