---
description: 'Dowiedz się więcej na temat: preprocesora'
title: Preprocesor
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: dd79766777926871e7bbf849f96420ef37052eba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202083"
---
# <a name="preprocessor"></a>Preprocesor

Preprocesor jest procesorem tekstowym, który manipuluje tekstem pliku źródłowego w pierwszej fazie tłumaczenia. Preprocesor nie przeanalizuje tekstu źródłowego, ale podzieli go na tokeny umożliwiające lokalizowanie wywołań makr. Chociaż kompilator zwykle wywołuje preprocesor podczas pierwszego przebiegu, preprocesor może być również wywoływany oddzielnie, aby przetwarzać tekst bez kompilowania.

Materiał referencyjny w preprocesorach zawiera następujące sekcje:

- [Dyrektywy preprocesora](../preprocessor/preprocessor-directives.md)

- [Operatory preprocesora](../preprocessor/preprocessor-operators.md)

- [Wstępnie zdefiniowane makra](../preprocessor/predefined-macros.md)

- [Pragma — dyrektywy](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**Specyficzne dla firmy Microsoft**

Możesz uzyskać listę kodu źródłowego po wstępnej przejściu przy użyciu opcji kompilatora [/e](../build/reference/e-preprocess-to-stdout.md) lub [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) . Obie opcje wywołują preprocesor i wysyłają wynikowy tekst do standardowego urządzenia wyjściowego, które w większości przypadków jest konsolą programu. Różnica między tymi dwiema opcjami `/E` obejmuje `#line` dyrektywy, a także `/EP` Paski te dyrektywy.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="special-terminology"></a><a name="_predir_special_terminology"></a> Specjalna terminologia

W dokumentacji preprocesora termin "argument" odwołuje się do jednostki, która jest przenoszona do funkcji. W niektórych przypadkach jest on modyfikowany przez "rzeczywiste" lub "formalne", który opisuje wyrażenie argumentu określone w wywołaniu funkcji i deklarację argumentu określoną odpowiednio w definicji funkcji.

Termin "zmienna" odnosi się do prostego obiektu danych typu C. Termin "Object" odnosi się zarówno do obiektów, jak i zmiennych języka C++. jest to termin włącznie.

## <a name="see-also"></a>Zobacz też

[Dokumentacja preprocesora języka C/C++](../preprocessor/c-cpp-preprocessor-reference.md)\
[Fazy tłumaczenia](../preprocessor/phases-of-translation.md)
