---
description: 'Dowiedz się więcej na temat: CWinApp i Kreator aplikacji MFC'
title: Klasa CWinApp i kreator aplikacji MFC
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
ms.openlocfilehash: 1ce1f0a84aa5a0f123f9fa8654d1ce286c47d1d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309267"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>Klasa CWinApp i kreator aplikacji MFC

Podczas tworzenia aplikacji szkieletowej Kreator aplikacji MFC deklaruje klasę aplikacji pochodzącą od [CWinApp](reference/cwinapp-class.md). Kreator aplikacji MFC generuje również plik implementacji zawierający następujące elementy:

- Mapa komunikatów dla klasy aplikacji.

- Pusty Konstruktor klasy.

- Zmienna, która deklaruje jeden i tylko obiekt klasy.

- Standardowa implementacja `InitInstance` funkcji składowej.

Klasa aplikacji jest umieszczana w nagłówku projektu i głównych plikach źródłowych. Nazwy tworzonych klas i plików są oparte na nazwie projektu dostarczanej w Kreatorze aplikacji MFC. Najprostszym sposobem wyświetlania kodu dla tych klas jest [Widok klasy](/visualstudio/ide/viewing-the-structure-of-code).

Dostarczone implementacje standardowe i mapa komunikatów są odpowiednie dla wielu celów, ale można je zmodyfikować w razie potrzeby. Najbardziej interesującymi tymi implementacjami jest `InitInstance` funkcja członkowska. Zazwyczaj należy dodać kod do implementacji szkieletowej `InitInstance` .

## <a name="see-also"></a>Zobacz też

[CWinApp: Klasa aplikacji](cwinapp-the-application-class.md)<br/>
[CWinApp funkcje członkowskie](overridable-cwinapp-member-functions.md)<br/>
[Specjalne usługi CWinApp](special-cwinapp-services.md)
