---
description: 'Dowiedz się więcej na temat: klasy bazowe'
title: Klasy podstawowe
ms.date: 11/19/2018
helpviewer_keywords:
- inheritance, multiple
- base classes [C++], virtual
- derived classes [C++], multiple bases
- multiple inheritance, base classes
- virtual base classes [C++]
- base classes [C++]
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
ms.openlocfilehash: 914a09817c29683123823acfff80c0428da6b2d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335620"
---
# <a name="base-classes"></a>Klasy podstawowe

Proces dziedziczenia tworzy nową klasę pochodną, która składa się z elementów członkowskich klasy podstawowej (ES) i nowych elementów członkowskich dodanych przez klasę pochodną. W przypadku wielokrotnego dziedziczenia możliwe jest konstruowanie wykresu dziedziczenia, gdzie taka sama klasa bazowa jest częścią więcej niż jednej klasy pochodnej. Na poniższej ilustracji przedstawiono ten wykres.

![Wiele wystąpień klasy bazowej](../cpp/media/vc38xn1.gif "Wiele wystąpień klasy bazowej") <br/>
Wiele wystąpień pojedynczej klasy podstawowej

Na rysunku przedstawiono ilustracjowe reprezentacje składników `CollectibleString` i `CollectibleSortable` . Jednak Klasa bazowa, `Collectible` , znajduje się w `CollectibleSortableString` `CollectibleString` ścieżce i `CollectibleSortable` ścieżce. Aby wyeliminować tę nadmiarowość, takie klasy mogą być deklarowane jako wirtualne klasy bazowe, gdy są dziedziczone.
