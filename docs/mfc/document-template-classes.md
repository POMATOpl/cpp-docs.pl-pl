---
title: Klasy szablonów dokumentów | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.document
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87984bf06d8ca178d2a21ac8ff475f828690668e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406064"
---
# <a name="document-template-classes"></a>Klasy szablonów dokumentów

Szablon dokumentu obiektów koordynacji tworzenia dokumentu, widoku i ramki okna obiektów, kiedy nowy dokument lub utworzony widok.

[CDocTemplate](../mfc/reference/cdoctemplate-class.md)<br/>
Klasa bazowa dla szablonów dokumentów. Nigdy nie użyjesz tej klasy bezpośrednio; Zamiast tego należy użyć jest jedną z innych szablonów dokumentów klas pochodzących z tej klasy.

[CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)<br/>
Szablon dla dokumentów w interfejsu wielu dokumentów (MDI). Aplikacje MDI mogą mieć wiele dokumentów, Otwórz w danym momencie.

[CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md)<br/>
Szablon służący do dokumentów interfejsu pojedynczego dokumentu (SDI). Aplikacje SDI mają tylko jeden dokument, Otwórz w danym momencie.

## <a name="related-class"></a>Klasy pokrewne

[CCreateContext](../mfc/reference/ccreatecontext-structure.md)<br/>
Struktura przekazywane przez szablon dokumentu do funkcji tworzenia okna do koordynowania Tworzenie obiektów dokumentu, widoku i ramki okna.

## <a name="see-also"></a>Zobacz też

[Klasa — Przegląd](../mfc/class-library-overview.md)

