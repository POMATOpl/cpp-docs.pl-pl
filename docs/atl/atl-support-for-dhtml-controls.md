---
description: 'Dowiedz się więcej o: Obsługa ATL dla formantów DHTML'
title: Obsługa ALT dla kontrolek DHTML
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
ms.openlocfilehash: 7527527bc5574470fd361bae2375c25ce9345f3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148593"
---
# <a name="atl-support-for-dhtml-controls"></a>Obsługa ALT dla kontrolek DHTML

Za pomocą biblioteki ATL można utworzyć formant z dynamiczną funkcją HTML (DHTML). Formant ATL DHTML:

- Hostuje formant WebBrowser.

- Określa, że za pomocą HTML, interfejs użytkownika (UI) kontrolki DHTML.

- Uzyskuje dostęp do obiektu WebBrowser i jego metod za pomocą interfejsu, [IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127\(v=vs.85\)).

- Zarządza komunikacją między kodem C++ i HTML.

Kontrolka DHTML jest podobna do dowolnej innej kontrolki ATL, z wyjątkiem tego, że kontrolka DHTML zawiera dodatkowy interfejs wysyłania. Zobacz rysunek w temacie [Identyfikowanie elementów projektu kontrolki DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md) dla ilustracji interfejsów podanych w domyślnym projekcie DHTML.

Formant ATL DHTML można wyświetlić w przeglądarce internetowej lub w innym kontenerze, takim jak kontener testu kontrolki ActiveX.

## <a name="in-this-section"></a>W tej sekcji

[Identyfikowanie elementów projektu kontrolki DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md)<br/>
Opisuje elementy projektu kontrolki DHTML.

[Wywoływanie kodu C++ z DHTML](../atl/calling-cpp-code-from-dhtml.md)<br/>
Zawiera przykład wywoływania kodu C++ z kontrolki DHTML.

[Tworzenie kontrolki DHTML ATL](../atl/creating-an-atl-dhtml-control.md)<br/>
Wyświetla listę kroków tworzenia kontrolki DHTML.

[Testowanie kontrolki DHTML ATL](../atl/testing-the-atl-dhtml-control.md)<br/>
Pokazuje, jak utworzyć i przetestować początkowy projekt kontrolki DHTML.

[Modyfikowanie kontrolki DHTML ATL](../atl/modifying-the-atl-dhtml-control.md)<br/>
Pokazuje, jak dodać niektóre funkcje do kontrolki.

[Testowanie zmienionej kontrolki DHTML ATL](../atl/testing-the-modified-atl-dhtml-control.md)<br/>
Pokazuje, jak utworzyć i przetestować dodaną funkcję kontrolki.

## <a name="related-sections"></a>Sekcje pokrewne

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Zawiera łącza do tematów koncepcyjnych dotyczących sposobu programowania przy użyciu Active Template Library.
