---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziomy 2 i 4) — od C4200'
title: Ostrzeżenie kompilatora (poziomy 2 i 4) — od C4200
ms.date: 11/04/2016
f1_keywords:
- C4200
helpviewer_keywords:
- C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
ms.openlocfilehash: 7068e98303049db4e64e46abbd9dae14c11395f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234348"
---
# <a name="compiler-warning-levels-2-and-4-c4200"></a>Ostrzeżenie kompilatora (poziomy 2 i 4) — od C4200

użyto niestandardowego rozszerzenia: tablica o rozmiarze zerowym w strukturze/Unii

Wskazuje, że struktura lub Unia zawiera tablicę o rozmiarze zerowym.

Deklaracja tablicy o rozmiarze zerowym jest rozszerzeniem firmy Microsoft. Powoduje to wyświetlenie ostrzeżenia poziomu 2 w przypadku skompilowania pliku języka C++ oraz ostrzeżenia poziomu 4 podczas kompilowania pliku C. Kompilacja języka C++ daje również następujące ostrzeżenie: "nie można wygenerować operatora Copy-ctor lub Copy-przypisania, gdy UDT zawiera tablicę o rozmiarze zerowym". Ten przykład generuje ostrzeżenie — od C4200:

```cpp
// C4200.cpp
// compile by using: cl /W4 c4200.cpp
struct A {
    int a[0];  // C4200
};
int main() {
}
```

To niestandardowe rozszerzenie jest często używane do interfejsu kodu z zewnętrznymi strukturami danych o zmiennej długości. Jeśli ten scenariusz ma zastosowanie do kodu, można wyłączyć Ostrzeżenie:

## <a name="example"></a>Przykład

```cpp
// C4200b.cpp
// compile by using: cl /W4 c4200a.cpp
#pragma warning(disable : 4200)
struct A {
    int a[0];
};
int main() {
}
```
