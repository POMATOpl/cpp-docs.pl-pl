---
description: 'Dowiedz się więcej na temat: stdext przestrzeń nazw'
title: stdext — Przestrzeń nazw
ms.date: 09/06/2017
f1_keywords:
- stdext
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
ms.openlocfilehash: bb81dde22014ec91f7212ce4313c21a8410f30a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153788"
---
# <a name="stdext-namespace"></a>stdext — Przestrzeń nazw

Elementy członkowskie [\<hash_map>](../standard-library/hash-map.md) [\<hash_set>](../standard-library/hash-set.md) plików nagłówkowych i nie są obecnie częścią standardu ISO C++. W związku z tym te typy i elementy członkowskie zostały przeniesione z `std` przestrzeni nazw do przestrzeni nazw `stdext` , aby pozostawały zgodne ze standardem C++.

Podczas kompilowania z [/ze](../build/reference/za-ze-disable-language-extensions.md), który jest domyślnym, kompilator ostrzega o użyciu `std` dla elementów członkowskich \<hash_map> i \<hash_set> plików nagłówkowych. Aby wyłączyć ostrzeżenie, użyj dyrektywy pragma [ostrzeżenia](../preprocessor/warning.md) .

Aby kompilator generował błąd do użycia `std` dla elementów członkowskich \<hash_map> i \<hash_set> plików nagłówkowych z **/ze**, Dodaj następującą dyrektywę przed `#include` wszystkimi plikami nagłówka biblioteki standardowej języka C++.

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

Podczas kompilowania z **/za** kompilator generuje błąd.

## <a name="see-also"></a>Zobacz też

[Omówienie standardowej biblioteki języka C++](../standard-library/cpp-standard-library-overview.md)
