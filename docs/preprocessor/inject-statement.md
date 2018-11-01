---
title: inject_statement
ms.date: 10/18/2018
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: cf7d06eddb5ae6d08f57fb82613d97c7dcc36074
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566715"
---
# <a name="injectstatement"></a>inject_statement

**Określonego język C++**

Wstawia jej argument jako tekst źródłowy do nagłówka biblioteki typów.

## <a name="syntax"></a>Składnia

```
inject_statement("source_text")
```

### <a name="parameters"></a>Parametry

*source_text*<br/>
Tekst źródłowy, który ma zostać wstawiony do pliku nagłówka biblioteki typów.

## <a name="remarks"></a>Uwagi

Tekst zostanie umieszczony na początku deklaracji przestrzeni nazw, który otacza zawartość biblioteki typów w pliku nagłówkowym.

**KONIEC określonego języka C++**

## <a name="see-also"></a>Zobacz też

[atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)