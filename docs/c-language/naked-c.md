---
description: 'Dowiedz się więcej o: Owies (C)'
title: Naked (C)
ms.date: 11/04/2016
helpviewer_keywords:
- naked keyword [C], storage-class attribute
- naked keyword [C]
- prolog code
- epilog code
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
ms.openlocfilehash: 8d45371f71ccffda2c7505587f0942671d24b047
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257020"
---
# <a name="naked-c"></a>Naked (C)

**Specyficzne dla firmy Microsoft**

Atrybut klasy magazynu owies to specyficzne dla firmy Microsoft rozszerzenie języka C. Kompilator generuje kod bez kodu prologu i epilogu dla funkcji zadeklarowanych z atrybutem klasy magazynu owies. Funkcje bez dodatków są przydatne, gdy trzeba napisać własne sekwencje kodu prologu/epilogu przy użyciu kodu asemblera wbudowanego. Funkcje inowies są przydatne do pisania sterowników urządzeń wirtualnych.

Aby uzyskać szczegółowe informacje na temat korzystania z atrybutu owies, zobacz informowanie [funkcji](../c-language/naked-functions.md).

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Rozszerzone atrybuty Storage-Class języka C](../c-language/c-extended-storage-class-attributes.md)
