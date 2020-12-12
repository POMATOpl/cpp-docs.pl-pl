---
description: 'Dowiedz się więcej na temat: dyrektywy preprocesora'
title: Dyrektywy preprocesora
ms.date: 11/04/2016
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
ms.openlocfilehash: 50691647436f492b329b6af43a626e933453d3a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213959"
---
# <a name="directives-to-the-preprocessor"></a>Dyrektywy preprocesora

"Dyrektywa" powoduje, że preprocesor C wykonuje konkretną akcję dla tekstu programu przed kompilacją. [Dyrektywy preprocesora](../preprocessor/preprocessor-directives.md) są w pełni opisane w *dokumentacji preprocesora*. Ten przykład używa dyrektywy preprocesora `#define` :

```
#define MAX 100
```

Ta instrukcja instruuje kompilator, aby zastąpił każde wystąpienie elementu `MAX` `100` przed kompilacją. Dyrektywy preprocesora kompilatora języka C są następujące:

|#define|#endif|#ifdef|#line|
|--------------|-------------|-------------|------------|
|`#elif`|`#error`|**#ifndef**|**#pragma**|
|`#else`|`#if`|`#include`|`#undef`|

## <a name="see-also"></a>Zobacz też

[Pliki źródłowe i programy źródłowe](../c-language/source-files-and-source-programs.md)
