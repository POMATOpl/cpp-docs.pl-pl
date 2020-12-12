---
description: 'Dowiedz się więcej na temat: arytmetyka wskaźnika'
title: Arytmetyczny wskaźnik
ms.date: 11/04/2016
helpviewer_keywords:
- pointer arithmetic
- arithmetic pointer
ms.assetid: eb924a29-59d3-48a5-9d62-9424790730eb
ms.openlocfilehash: 37ee9fd696f874d1faa84b5d656317cf67f75a6c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243123"
---
# <a name="pointer-arithmetic"></a>Arytmetyczny wskaźnik

Operacje dodatków obejmujące wskaźnik i liczbę całkowitą dają znaczące wyniki tylko wtedy, gdy argument operacji wskaźnika odnosi się do elementu członkowskiego tablicy, a wartość całkowita generuje przesunięcie w granicach tej samej tablicy. Gdy wartość całkowita zostanie przekonwertowana na przesunięcie adresu, kompilator zakłada, że tylko pozycje pamięci o tym samym rozmiarze mieszczą się w oryginalnym adresie i adresie i przesunięciu.

To założenie jest prawidłowe dla elementów członkowskich tablicy. Według definicji tablica jest serią wartości tego samego typu; jego elementy znajdują się w ciągłej lokalizacji pamięci. Jednak magazyn dla dowolnego typu, z wyjątkiem elementów tablicy, nie jest gwarantowany przez ten sam typ identyfikatorów. Oznacza to, że wartości puste mogą znajdować się między pozycjami pamięci, nawet pozycjami tego samego typu. W związku z tym wyniki dodawania lub odejmowania z adresów wszelkich wartości, ale nie są zdefiniowane.

Podobnie, gdy dwie wartości wskaźnika są odejmowane, konwersja zakłada, że tylko wartości tego samego typu, bez żadnych pustych, mieszczą się między adresami podaną przez operandy.

## <a name="see-also"></a>Zobacz też

[Operatory addytywne języka C](../c-language/c-additive-operators.md)
