---
description: Dowiedz się więcej na temat Document-Template klas
title: Klasy szablonów dokumentów
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
ms.openlocfilehash: f9e67cc8f6a115345f6b1f42c2064fcbed7be47e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330279"
---
# <a name="document-template-classes"></a>Klasy szablonów dokumentów

Obiekty szablonu dokumentu koordynują Tworzenie obiektów dokumentów, widoków i okien ramowych podczas tworzenia nowego dokumentu lub widoku.

[CDocTemplate](reference/cdoctemplate-class.md)<br/>
Klasa bazowa dla szablonów dokumentów. Nigdy nie będziesz używać tej klasy bezpośrednio; Zamiast tego należy użyć jednej z innych klas szablonów dokumentu pochodnych od tej klasy.

[CMultiDocTemplate](reference/cmultidoctemplate-class.md)<br/>
Szablon dokumentów w interfejsie wielu dokumentów (MDI). Aplikacje MDI mogą mieć otwarte jednocześnie wiele dokumentów.

[CSingleDocTemplate](reference/csingledoctemplate-class.md)<br/>
Szablon dokumentów w interfejsie pojedynczego dokumentu (SDI). Aplikacje SDI mają otwarty tylko jeden dokument w danym momencie.

## <a name="related-class"></a>Powiązana Klasa

[CCreateContext](reference/ccreatecontext-structure.md)<br/>
Struktura przenoszona przez szablon dokumentu do funkcji tworzenia okna w celu koordynowania tworzenia obiektów dokumentów, widoków i okien ramowych.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](class-library-overview.md)
