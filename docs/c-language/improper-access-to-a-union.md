---
description: 'Dowiedz się więcej na temat: niewłaściwy dostęp do Unii'
title: Niewłaściwy dostęp do złożenia
ms.date: 11/04/2016
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
ms.openlocfilehash: edff4d74e4e31b505e8c6b71555358fcd4b7e070
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182115"
---
# <a name="improper-access-to-a-union"></a>Niewłaściwy dostęp do złożenia

**3.3.2.3 ANSI** Do elementu członkowskiego obiektu Union uzyskuje się dostęp przy użyciu elementu członkowskiego innego typu

Jeśli jest zadeklarowana Unia dwóch typów i jest przechowywana jedna wartość, a Unia jest dostępna z innym typem, wyniki są niezawodne.

Na przykład Unia **`float`** i **`int`** jest zadeklarowana. **`float`** Wartość jest przechowywana, ale program później uzyskuje dostęp do wartości jako **`int`** . W takiej sytuacji wartość będzie zależeć od wewnętrznego magazynu **`float`** wartości. Wartość całkowita nie będzie godna zaufania.

## <a name="see-also"></a>Zobacz też

[Struktury, złożenia, wyliczenia i pola bitowe](../c-language/structures-unions-enumerations-and-bit-fields.md)
