---
description: 'Dowiedz się więcej na temat: Container Class:: Erase'
title: Kontener Class::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 7e9d7747237a38c42bfb7a39c5d5e66cc8a44608
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324870"
---
# <a name="container-classerase"></a>Kontener Class::erase

> [!NOTE]
> Ten temat znajduje się w dokumentacji języka Microsoft C++ jako niefunkcjonalny przykład kontenerów używanych w standardowej bibliotece języka C++. Aby uzyskać więcej informacji, zobacz [kontenery standardowej biblioteki języka C++](../standard-library/stl-containers.md).

Usuwa element.

## <a name="syntax"></a>Składnia

```cpp
iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>Uwagi

Pierwsza funkcja członkowska usuwa element kontrolowanej sekwencji wskazywany przez *_Where*. Druga funkcja członkowska usuwa elementy z kontrolowanej sekwencji z zakresu [ `first` , `last` ). Oba zwracają iterator, który wyznacza pierwszy element pozostały poza elementami usuniętymi lub [kończy](../standard-library/container-class-end.md) , jeśli taki element nie istnieje.

Funkcje członkowskie zwracają wyjątek tylko wtedy, gdy operacja kopiowania zgłasza wyjątek.

## <a name="see-also"></a>Zobacz też

[Przykładowa Klasa kontenera](../standard-library/sample-container-class.md)
