---
title: 'Instrukcje: Deklarowanie unieruchamiania wskaźników i typów wartości'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- value types, declaring
- pinning pointers
ms.assetid: 57c5ec8a-f85a-48c4-ba8b-a81268bcede0
ms.openlocfilehash: 2f62d8e93af48d0d916349f7c58fbd5fe445e322
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787424"
---
# <a name="how-to-declare-pinning-pointers-and-value-types"></a>Instrukcje: Deklarowanie unieruchamiania wskaźników i typów wartości

Typ wartości może być zapakowany niejawnie. Następnie można zadeklarować przypinania wskaźnik do obiektu typu wartościowego sam i użycia **pin_ptr** typem wartości spakowanej.

## <a name="example"></a>Przykład

### <a name="code"></a>Kod

```cpp
// pin_ptr_value.cpp
// compile with: /clr
value struct V {
   int i;
};

int main() {
   V ^ v = gcnew V;   // imnplicit boxing
   v->i=8;
   System::Console::WriteLine(v->i);
   pin_ptr<V> mv = &*v;
   mv->i = 7;
   System::Console::WriteLine(v->i);
   System::Console::WriteLine(mv->i);
}
```

```Output
8
7
7
```

## <a name="see-also"></a>Zobacz też

[pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)