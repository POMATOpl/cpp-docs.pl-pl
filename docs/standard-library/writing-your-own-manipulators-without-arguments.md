---
description: 'Dowiedz się więcej na temat: pisania własnych operacji manipulowania bez argumentów'
title: Tworzenie manipulatorów bez argumentów
ms.date: 11/04/2016
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
ms.openlocfilehash: 593db0a3dacb54c94cc865ebc20b1e1b39d2c208
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187757"
---
# <a name="writing-your-own-manipulators-without-arguments"></a>Tworzenie manipulatorów bez argumentów

Pisanie manipulowania, które nie używają argumentów, nie wymaga klasy pochodnej ani nie korzysta ze złożonych makr. Załóżmy, że drukarka wymaga pary \<ESC> [aby wprowadzić tryb pogrubiony. Tę parę można wstawić bezpośrednio do strumienia:

```cpp
cout << "regular " << '\033' << '[' << "boldface" << endl;
```

Można też zdefiniować `bold` manipulator, który wstawia znaki:

```cpp
ostream& bold(ostream& os) {
    return os << '\033' << '[';
}
cout << "regular " << bold << "boldface" << endl;
```

Funkcja zdefiniowana globalnie `bold` przyjmuje `ostream` argument odwołania i zwraca `ostream` odwołanie. Nie jest to funkcja członkowska ani zaprzyjaźniona, ponieważ nie potrzebuje dostępu do żadnych prywatnych elementów klasy. `bold`Funkcja nawiązuje połączenie ze strumieniem, ponieważ `<<` operator strumienia jest przeciążony do akceptowania tego typu funkcji przy użyciu deklaracji, która wygląda następująco:

```cpp
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))
{
    // call ios_base manipulator
    (*_Pfn)(*(ios_base *)this);

    return (*this);
}
```

Za pomocą tej funkcji można rozłożyć inne przeciążone operatory. W tym przypadku jest to przypadkowe, które `bold` wstawia znaki do strumienia. Funkcja jest wywoływana, gdy zostanie wstawiona do strumienia, niekoniecznie po wydrukowaniu sąsiadujących znaków. W związku z tym drukowanie może być opóźnione ze względu na buforowanie strumienia.

## <a name="see-also"></a>Zobacz też

[Strumienie wyjściowe](../standard-library/output-streams.md)
