---
description: 'Dowiedz się więcej na temat: operatory preprocesora'
title: Operatory preprocesora
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
ms.openlocfilehash: 960531a32dd8b4f834117fb01272e2ed45fecf92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202096"
---
# <a name="preprocessor-operators"></a>Operatory preprocesora

Cztery operatory specyficzne dla preprocesora są używane w kontekście `#define` dyrektywy. W poniższej tabeli przedstawiono podsumowanie każdego z nich. Operatory tworzenia ciągu, konwersji na znaki i wklejania tokenu zostały omówione w następnych trzech sekcjach. Aby uzyskać informacje na temat `defined` operatora, zapoznaj [się z dyrektywami #if, #elif, #else i #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

|Operator|Akcja|
|--------------|------------|
|[Operator tworzenia ciągów (#)](../preprocessor/stringizing-operator-hash.md)|Powoduje, że odpowiadający mu rzeczywisty argument ma być ujęty w znaki podwójnego cudzysłowu|
|[Operator konwersji na znaki (#@)](../preprocessor/charizing-operator-hash-at.md)|Powoduje, że odpowiadający argument może być ujęty w znaki pojedynczego cudzysłowu i być traktowany jako znak (specyficzny dla firmy Microsoft)|
|[Operator wklejania tokenu (##)](../preprocessor/token-pasting-operator-hash-hash.md)|Zezwala na używanie tokenów jako rzeczywistych argumentów do tworzenia innych tokenów|
|[zdefiniowany operator](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Upraszcza pisanie wyrażeń złożonych w niektórych dyrektywach makra|

## <a name="see-also"></a>Zobacz też

[Dyrektywy preprocesora](../preprocessor/preprocessor-directives.md)\
[Wstępnie zdefiniowane makra](../preprocessor/predefined-macros.md)\
[Dokumentacja preprocesora języka c/c++](../preprocessor/c-cpp-preprocessor-reference.md)
