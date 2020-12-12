---
description: 'Dowiedz się więcej o programie: serwery'
title: Serwery
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC]
- OLE server applications [MFC], activation
- full-server
- servers
- mini-server
- OLE server applications [MFC], server types
- server applications [MFC]
ms.assetid: e45172e8-eae3-400a-8139-0fa009a42fdc
ms.openlocfilehash: 5e9a9dd7cbb1ab237712b5ad0c84e3114a119ee3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217305"
---
# <a name="servers"></a>Serwery

Aplikacja serwera (lub aplikacja składników) tworzy elementy OLE (lub składniki) do użycia przez aplikacje kontenera. Aplikacja serwera edycji wizualnej obsługuje również edycję wizualną lub aktywację w miejscu. Inną formą serwera OLE jest [serwer automatyzacji](../mfc/automation-servers.md). Niektóre aplikacje serwera obsługują tylko tworzenie elementów osadzonych; inne obsługują tworzenie zarówno elementów osadzonych, jak i połączonych. Niektóre obsługują tylko łączenie, chociaż jest to rzadkie. Wszystkie aplikacje serwera muszą obsługiwać aktywację przez aplikacje kontenera, gdy użytkownik chce edytować element. Aplikacja może być zarówno kontenerem, jak i serwerem. Innymi słowy, może zarówno uwzględnić dane w swoich dokumentach, jak i utworzyć dane, które można dołączyć jako elementy do dokumentów innych aplikacji.

Miniserver to specjalny typ aplikacji serwerowej, który może być uruchamiany tylko przez kontener. Microsoft Draw i Microsoft Graph są przykładami miniservers. Miniserver nie przechowuje dokumentów jako plików na dysku. Zamiast tego odczytuje dokumenty z i zapisuje je do elementów w dokumentach należących do kontenerów. W efekcie miniserver obsługuje tylko osadzanie, a nie łączenie.

Pełny serwer może być uruchamiany jako aplikacja autonomiczna lub uruchomiona przez aplikację kontenera. Pełny serwer może przechowywać dokumenty jako pliki na dysku. Może obsługiwać tylko osadzanie, osadzanie i łączenie lub łączenie. Użytkownik aplikacji kontenera może utworzyć element osadzony, wybierając polecenie Wytnij lub Kopiuj na serwerze i polecenie Wklej w kontenerze. Połączony element jest tworzony przez wybranie polecenia Kopiuj na serwerze i polecenie Wklej łącze w kontenerze. Alternatywnie użytkownik może utworzyć osadzony lub połączony element przy użyciu okna dialogowego Wstaw obiekt.

Poniższa tabela zawiera podsumowanie cech różnych typów serwerów:

### <a name="server-characteristics"></a>Właściwości serwera

|Typ serwera|Obsługuje wiele wystąpień|Elementy na dokument|Dokumenty na wystąpienie|
|--------------------|---------------------------------|------------------------|----------------------------|
|Miniserver|Tak|1|1|
|Pełny serwer SDI|Tak|1 (jeśli jest obsługiwane łączenie, 1 lub więcej)|1|
|Pełny serwer MDI|Nie (niewymagane)|1 (jeśli jest obsługiwane łączenie, 1 lub więcej)|0 lub więcej|

Aplikacja serwera powinna obsługiwać wiele kontenerów jednocześnie, w przypadku, gdy więcej niż jeden kontener będzie używany do edycji osadzonego lub połączonego elementu. Jeśli serwer jest aplikacją SDI (lub miniserver z interfejsem okna dialogowego), wiele wystąpień serwera musi działać jednocześnie. Dzięki temu osobne wystąpienie aplikacji może obsłużyć każde żądanie kontenera.

Jeśli serwer jest aplikacją MDI, można utworzyć nowe okno podrzędne MDI za każdym razem, gdy kontener wymaga edytowania elementu. W ten sposób pojedyncze wystąpienie aplikacji może obsługiwać wiele kontenerów.

Aplikacja serwera musi informować o systemowej biblioteki DLL, co należy zrobić, jeśli jedno wystąpienie serwera jest już uruchomione, gdy inny kontener żąda swoich usług: czy należy uruchomić nowe wystąpienie serwera lub skierować żądania wszystkich kontenerów do jednego wystąpienia serwera.

Aby uzyskać więcej informacji na temat serwerów, zobacz:

- [Serwery: implementowanie serwera](../mfc/servers-implementing-a-server.md)

- [Serwery: implementowanie dokumentów serwera](../mfc/servers-implementing-server-documents.md)

- [Serwery: implementowanie okien ramowych In-Place](../mfc/servers-implementing-in-place-frame-windows.md)

- [Serwery: elementy serwera](../mfc/servers-server-items.md)

- [Serwery: problemy z User-Interface](../mfc/servers-user-interface-issues.md)

## <a name="see-also"></a>Zobacz też

[OLE](../mfc/ole-in-mfc.md)<br/>
[Containers](../mfc/containers.md)<br/>
[Kontenery: funkcje zaawansowane](../mfc/containers-advanced-features.md)<br/>
[Menu i zasoby (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Rejestracja](../mfc/registration.md)<br/>
[Serwery automatyzacji](../mfc/automation-servers.md)
