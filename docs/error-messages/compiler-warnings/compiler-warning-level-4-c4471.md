---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4471'
title: Ostrzeżenie kompilatora (poziom 4) C4471
ms.date: 04/24/2017
f1_keywords:
- C4471
helpviewer_keywords:
- C4471
ms.assetid: ccfd8bd5-bc1b-4be7-a6ea-0e3a7add6607
ms.openlocfilehash: cef492bf8aab33f46b3f590a13ffa5462a7ca41d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203500"
---
# <a name="compiler-warning-level-4-c4471"></a>Ostrzeżenie kompilatora (poziom 4) C4471

"*Wyliczenie*": Deklaracja do przodu wyliczenia nienależącego do zakresu musi mieć typ podstawowy (założono int)

Nie znaleziono deklaracji do przodu wyliczenia nienależącego do zakresu bez specyfikatora dla typu źródłowego. Domyślnie Visual C++ zakłada się, **`int`** że jest typem podstawowym dla wyliczenia. Może to powodować problemy, jeśli inny typ jest używany w definicji wyliczenia, na przykład, jeśli określono inny jawny typ lub inny typ jest niejawnie ustawiany przez inicjatora. Możesz również mieć problemy z przenośnością; Inne kompilatory nie zakładają **`int`** , że jest podstawowym typem wyliczenia.

To ostrzeżenie jest domyślnie wyłączone; Możesz użyć/Wall lub/w *N* 4471, aby włączyć go w wierszu polecenia, lub użyć [ostrzeżenia](../../preprocessor/warning.md) #pragma w pliku źródłowym.

## <a name="examples"></a>Przykłady

W niektórych przypadkach to ostrzeżenie jest fałszywe. Jeśli deklaracja do przodu dla wyliczenia zostanie wyświetlona po definicji, to ostrzeżenie może zostać wywołane. Na przykład ten kod jest prawidłowy, mimo że może to spowodować C4471:

```cpp
// C4471a.cpp
// Compile with: cl /c /w14471 C4471a.cpp
enum Example { item = 0x80000000UL };
enum Example;    // Spurious C4471
// ...
```

Ogólnie rzecz biorąc, można bezpiecznie użyć pełnej definicji dla wyliczenia nienależącego do zakresu zamiast deklaracji do przodu. Można umieścić definicję w pliku nagłówkowym i uwzględnić ją w plikach źródłowych, które odwołują się do niego. Działa to w kodzie zapisanym dla języka C++ 98 i nowszych. Zalecamy używanie tego rozwiązania do przenośności i łatwości konserwacji.

```cpp
// C4471b.cpp
// Compile with: cl /c /w14471 C4471b.cpp
enum Example;    // C4471
// To fix, replace the line above with the enumeration definition:
// enum Example { item = 0x80000000UL };
// ...
```

W języku C++ 11 można dodać jawny typ do wyliczenia nienależącego do zakresu i do jego deklaracji do przodu. Zalecamy to rozwiązanie tylko wtedy, gdy złożona logika dołączania nagłówka uniemożliwia użycie definicji zamiast deklaracji do przodu. To rozwiązanie może prowadzić do problemów z konserwacją: Jeśli zmienisz typ podstawowy używany do definicji wyliczenia, musisz również zmienić wszystkie deklaracje przesyłania dalej, aby dopasować, lub w kodzie mogą występować błędy dyskretne. Aby zminimalizować ten problem, można umieścić deklarację przekazującą do pliku nagłówkowego.

```cpp
// C4471c.cpp
// Client code for enumeration defined in C4471d.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example;    // C4471, int assumed
// To fix, replace the lines above with the forward declarations:
// enum Example : unsigned;
// ...
```

```cpp
// C4471d.cpp
// Definition for enumeration used in C4471c.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example : unsigned { item = 0x80000000 }; // explicit type
// ...
```

Jeśli określisz typ jawny dla wyliczenia, zalecamy również włączenie [C4369](compiler-warning-level-1-C4369.md)z ostrzeżeniem, który jest domyślnie włączony. Wskazuje przypadki, w których element wyliczenia wymaga innego typu niż jawnie określony typ.

Można zmienić kod w taki sposób, aby używał wyliczenia w zakresie, funkcji, która jest nowa w języku C++ 11. Należy zmienić zarówno definicję, jak i kod klienta używający typu wyliczenia, aby użyć wyliczenia w zakresie. Zalecamy użycie wyliczenia w zakresie w przypadku problemów ze zanieczyszczeniem przestrzeni nazw, ponieważ nazwy zdefiniowanych elementów wyliczenia są ograniczone do zakresu wyliczenia. Inną funkcją wyliczenia w zakresie jest to, że jego składowe nie mogą zostać niejawnie przekonwertowane na inny typ całkowity lub wyliczeniowy, który może być źródłem błędów o niewielkim stopniu.

```cpp
// C4471e.cpp
// Client code for scoped enumeration defined in C4471f.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum Example;    // C4471
// To fix, replace the line above with the forward declaration:
// enum class Example;
// ...
```

```cpp
// C4471f.cpp
// Definition for scoped enumeration used in C4471e.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum class Example { item = 0 };
// ...
```
