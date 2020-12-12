---
description: 'Dowiedz się więcej na temat: konwersje przypisań'
title: Konwersje przypisań
ms.date: 11/04/2016
helpviewer_keywords:
- conversions, assignment
- assignment conversions
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
ms.openlocfilehash: b9889214f160c981c57fc3174b542396d71458bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97279965"
---
# <a name="assignment-conversions"></a>Konwersje przypisań

W operacjach przypisywania typ przypisanej wartości jest konwertowany na typ zmiennej, która otrzymuje przypisanie. Język C umożliwia konwersje przez przypisanie między typami całkowitymi i zmiennoprzecinkowymi, nawet jeśli informacje zostaną utracone podczas konwersji. Używana metoda konwersji zależy od typów należących do przypisania, zgodnie z opisem w [zwykłych konwersje arytmetyczne](../c-language/usual-arithmetic-conversions.md) i w następujących sekcjach:

- [Konwersje z podpisanych typów całkowitych](../c-language/conversions-from-signed-integral-types.md)

- [Konwersje z niepodpisanych typów całkowitych](../c-language/conversions-from-unsigned-integral-types.md)

- [Konwersje z typów zmiennoprzecinkowych](../c-language/conversions-from-floating-point-types.md)

- [Konwersje do i z typów wskaźnika](../c-language/conversions-to-and-from-pointer-types.md)

- [Konwersje z innych typów](../c-language/conversions-from-other-types.md)

Kwalifikatory typu nie wpływają na dopuszczanie konwersji, chociaż **`const`** nie można użyć wartości l po lewej stronie przypisania.

## <a name="see-also"></a>Zobacz też

[Konwersje typów](../c-language/type-conversions-c.md)
