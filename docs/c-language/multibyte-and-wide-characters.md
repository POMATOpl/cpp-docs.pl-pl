---
description: 'Dowiedz się więcej na temat: znaków wielobajtowych i szerokich'
title: Znaki wielobajtowe i dwubajtowe
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- character data types [C]
- Unicode [C++], wide character set
- types [C], character
- characters [C++], wide
- international applications [C++], character display
- multibyte characters [C++]
- wide characters [C++]
- characters [C++], codes
- character codes [C++], wide
- character codes [C++], multibyte
ms.assetid: 1943c469-200d-4724-b18f-781d70520f9e
ms.openlocfilehash: 48063824b66df42d41b51ca491b0eec5f7679274
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243396"
---
# <a name="multibyte-and-wide-characters"></a>Znaki wielobajtowe i dwubajtowe

Znak wielobajtowy jest znakiem składającym się z sekwencji z co najmniej jednego bajtu. Każda sekwencja bajtów reprezentuje pojedynczy znak w rozszerzonym zestawie znaków. Znaki wielobajtowe są używane w zestawach znaków, takich jak kanji.

Znaki dwubajtowe są wielojęzycznymi kodami znaków, które są zawsze o 16 bitów. Typem dla stałych znaków jest **`char`** ; w przypadku znaków dwubajtowych typem jest **`wchar_t`** . Ze względu na to, że znaki dwubajtowe są zawsze stałym rozmiarem, używanie znaków dwubajtowych upraszcza programowanie przy użyciu międzynarodowych zestawów znaków

Literał ciągu znaków dwubajtowych jest `L"hello"` tablicą sześciu liczb całkowitych typu **`wchar_t`** .

```
{L'h', L'e', L'l', L'l', L'o', 0}
```

Specyfikacja Unicode jest specyfikacją dla znaków dwubajtowych. Procedury biblioteki wykonawczej do translacji między znakami wielobajtowymi i szerokimi obejmują `mbstowcs` , `mbtowc` , `wcstombs` , i `wctomb` .

## <a name="see-also"></a>Zobacz też

[Identyfikatory języka C](../c-language/c-identifiers.md)
