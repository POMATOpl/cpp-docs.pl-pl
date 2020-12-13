---
description: 'Dowiedz się więcej o: identyfikowaniu elementów projektu kontrolki DHTML'
title: Identyfikowanie elementów projektu kontrolki DHTML
ms.date: 11/19/2018
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
ms.openlocfilehash: 7f04857378564a86fc875e9874b79f6ae6c6a625
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148021"
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>Identyfikowanie elementów projektu kontrolki DHTML

Większość kodów formantów DHTML jest dokładnie taka, jak, która została utworzona dla dowolnej kontrolki ATL. Aby zapoznać się z podstawową wiedzą o kodzie ogólnym, zapoznaj się z [samouczkiem ATL](../atl/active-template-library-atl-tutorial.md)i przeczytaj sekcje [tworzenia projektu ATL](../atl/reference/creating-an-atl-project.md) i [podstawowe elementy ATL com](../atl/fundamentals-of-atl-com-objects.md).

Kontrolka DHTML jest podobna do dowolnej kontrolki ATL, z wyjątkiem:

- Oprócz zwykłych interfejsów, które implementuje formant, implementuje on dodatkowy interfejs, który jest używany do komunikacji między kodem C++ i interfejsem użytkownika HTML (UI). Interfejs użytkownika HTML wywołuje kod języka C++ przy użyciu tego interfejsu.

- Tworzy zasób HTML dla interfejsu użytkownika kontrolki.

- Umożliwia dostęp do modelu obiektów DHTML za pomocą zmiennej składowej `m_spBrowser` , która jest inteligentnym wskaźnikiem typu [IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127\(v=vs.85\)). Użyj tego wskaźnika, aby uzyskać dostęp do dowolnej części modelu obiektów DHTML.

Poniższa ilustracja ilustruje relacje między biblioteką DLL, kontrolką DHTML, przeglądarką internetową i zasobem HTML.

![Elementy projektu kontrolki DHTML](../atl/media/vc52en1.gif "Elementy projektu kontrolki DHTML")

> [!NOTE]
> Nazwy na tej grafice są symbolami zastępczymi. Nazwy zasobów HTML i interfejsy uwidocznione na formancie są oparte na nazwach, które zostały przypisane do kreatora kontrolki ATL.

Na tej ilustracji elementy są:

- **Moja biblioteka DLL** Biblioteka DLL utworzona przy użyciu Kreatora projektu ATL.

- **Kontrolka DHTML** ( `m_spBrowser` ) kontrolka DHTML utworzona przy użyciu kreatora obiektów ATL. Ta kontrolka uzyskuje dostęp do obiektu przeglądarki sieci Web i jego metod za pomocą interfejsu obiektu przeglądarki sieci Web `IWebBrowser2` . Sam formant ujawnia dwa następujące interfejsy, oprócz innych standardowych interfejsów wymaganych przez formant.

  - `IDHCTL1` Interfejs uwidoczniony przez formant do użycia tylko przez kontener.

  - `IDHCTLUI1` Interfejs wysyłania do komunikacji między kodem C++ i interfejsem użytkownika HTML. Przeglądarka sieci Web używa interfejsu wysyłania kontrolki do wyświetlania formantu. Można wywołać różne metody tego interfejsu wysyłania z interfejsu użytkownika kontrolki przez wywołanie `window.external` , a następnie nazwę metody w tym interfejsie wysyłania, który ma zostać wywołany. Będziesz mieć dostęp `window.external` ze znacznika skryptu w kodzie HTML, który tworzy interfejs użytkownika dla tej kontrolki. Aby uzyskać więcej informacji na temat wywoływania metod zewnętrznych w pliku zasobów, zobacz [Wywoływanie kodu C++ z języka DHTML](../atl/calling-cpp-code-from-dhtml.md).

- **IDR_CTL1** Identyfikator zasobu dla zasobu HTML. Nazwa pliku w tym przypadku jest DHCTL1UI.htm. Kontrolka DHTML używa zasobu HTML, który zawiera standardowe Tagi HTML i polecenia wysyłania okna zewnętrznego, które można edytować za pomocą edytora tekstu.

- **Przeglądarka sieci Web** Przeglądarka sieci Web wyświetla interfejs użytkownika kontrolki na podstawie kodu HTML w zasobie HTML. Wskaźnik do interfejsu przeglądarki sieci Web `IWebBrowser2` jest dostępny w kontrolce DHTML, aby umożliwić dostęp do modelu obiektów DHTML.

Kreator kontrolki ATL generuje formant z domyślnym kodem w ramach zasobu HTML i pliku. cpp. Można skompilować i uruchomić formant zgodnie z wygenerowanym przez kreatora, a następnie wyświetlić formant w przeglądarce sieci Web lub kontenera testów ActiveX. Na poniższej ilustracji przedstawiono domyślną kontrolkę ATL DHTML z trzema przyciskami wyświetlanymi w kontenerze testów:

![Formant ATL DHTML](../atl/media/vc52en2.gif "Formant ATL DHTML")

Zobacz [Tworzenie kontrolki DHTML ATL](../atl/creating-an-atl-dhtml-control.md) , aby rozpocząć tworzenie kontrolki DHTML. Zobacz [testowanie właściwości i zdarzeń za pomocą kontenera testów,](../mfc/testing-properties-and-events-with-test-container.md) Aby uzyskać informacje na temat uzyskiwania dostępu do kontenera testowego.

## <a name="see-also"></a>Zobacz też

[Obsługa formantów DHTML](../atl/atl-support-for-dhtml-controls.md)
