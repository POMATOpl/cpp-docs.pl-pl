---
description: 'Dowiedz się więcej na temat: jak skonwertować istniejącą Wstążkę MFC na zasób wstążki'
title: 'Porady: konwertowanie istniejącej wstążki MFC na zasób wstążki'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
ms.openlocfilehash: 825b8b4e3322afd8919ffad0f5e0f73c9d52be78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290287"
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>Porady: konwertowanie istniejącej wstążki MFC na zasób wstążki

Zasoby wstążki są łatwiejsze do wizualizacji, modyfikowania i konserwowania niż ręcznie zakodowane wstążki. W tym temacie opisano sposób konwertowania ręcznie zakodowanej wstążki w projekcie MFC do zasobu wstążki.

Musisz mieć istniejący projekt MFC, który ma kod korzystający z klas wstążki MFC, na przykład [Klasa CMFCRibbonBar](reference/cmfcribbonbar-class.md).

### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>Aby skonwertować Wstążkę MFC na zasób wstążki

1. W programie Visual Studio, w istniejącym projekcie MFC, Otwórz plik źródłowy, w którym `CMFCRibbonBar` obiekt jest zainicjowany. Zwykle plik to MainFrm. cpp. Dodaj następujący kod po kodzie inicjalizacji wstążki.

```
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");
```

   Zapisz i zamknij plik.

1. Skompiluj i uruchom aplikację MFC, a następnie w Notatniku otwórz RibbonOutput.txt i skopiuj jej zawartość.

1. W programie Visual Studio w menu **projekt** kliknij polecenie **Dodaj zasób**. W oknie dialogowym **Dodawanie zasobu** wybierz **Wstążkę** , a następnie kliknij przycisk **Nowy**.

   Program Visual Studio tworzy zasób wstążki i otwiera go w widoku projektu. Identyfikator zasobu wstążki to IDR_RIBBON1, który jest wyświetlany w **Widok zasobów**. Wstążka jest zdefiniowana w pliku XML Ribbon1. mfcribbon-ms.

1. W programie Visual Studio Otwórz Ribbon1. mfcribbon-ms, usuń jego zawartość, a następnie wklej zawartość RibbonOutput.txt, która została wcześniej skopiowana. Zapisz i Zamknij Ribbon1. mfcribbon-ms.

1. Ponownie otwórz plik źródłowy, w którym zainicjowano obiekt CMFCRibbonBar (zazwyczaj MainFrm. cpp) i Dodaj komentarz do istniejącego kodu wstążki. Dodaj następujący kod po komentarzu do kodu.

```
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
```

1. Skompiluj projekt i uruchom program.

## <a name="see-also"></a>Zobacz też

[Projektant wstążki (MFC)](ribbon-designer-mfc.md)
