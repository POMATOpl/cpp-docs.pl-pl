---
description: 'Dowiedz się więcej na temat: podstawowe informacje o technologii OLE: kontenery i serwery'
title: 'Podstawy OLE: kontenery i serwery'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE full-server applications [MFC]
- server applications [MFC], communication with containers
- full-server [MFC]
- server applications [MFC], requirements
- server applications [MFC], defined
- OLE server applications [MFC], about server applications
- server applications [MFC], full-server vs. mini-server
- OLE server applications [MFC], mini-server applications
- OLE containers [MFC], container applications
- containers [MFC], OLE container applications
- server applications [MFC]
ms.assetid: dafbb31d-096c-4654-b774-12900d832919
ms.openlocfilehash: 3ea578ce14165b16e84520b22bc545fc5d2a8882
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254780"
---
# <a name="ole-background-containers-and-servers"></a>Podstawy OLE: kontenery i serwery

Aplikacja kontenera to aplikacja, która może zawierać osadzone lub połączone elementy w swoich własnych dokumentach. Dokumenty zarządzane przez aplikację kontenera muszą mieć możliwość przechowywania i wyświetlania składników dokumentu OLE oraz danych utworzonych przez samą aplikację. Aplikacja kontenera musi również zezwalać użytkownikom na wstawianie nowych elementów lub edytowanie istniejących elementów przez Aktywowanie aplikacji serwera w razie potrzeby. Wymagania dotyczące interfejsu użytkownika aplikacji kontenera znajdują się w [kontenerze artykułu: User-Interface problemy](containers-user-interface-issues.md).

Aplikacja serwera lub aplikacja składników to aplikacja, która może tworzyć składniki dokumentu OLE do użycia przez aplikacje kontenerów. Aplikacje serwera zwykle obsługują przeciąganie i upuszczanie lub kopiowanie danych do schowka, dzięki czemu aplikacja kontenera może wstawić dane jako osadzony lub połączony element. Aplikacja może być zarówno kontenerem, jak i serwerem.

Większość serwerów to aplikacje autonomiczne lub pełne serwery; mogą być uruchamiane jako aplikacje autonomiczne lub mogą być uruchamiane przez aplikację kontenera. Miniserver to specjalny typ aplikacji serwerowej, która może być uruchamiana tylko przez kontener. Nie można jej uruchomić jako aplikacji autonomicznej. Serwery Microsoft Draw i Microsoft Graph są przykładami miniservers.

Kontenery i serwery nie komunikują się bezpośrednio. Zamiast tego komunikują się za pośrednictwem systemowych bibliotek dołączanych dynamicznie (DLL). Te biblioteki DLL udostępniają funkcje, które są wywoływane przez kontenery i serwery, a kontenery i serwery zapewniają funkcje wywołania zwrotnego, które są wywoływane przez biblioteki DLL.

Za pomocą tych środków komunikacji kontener nie musi znać szczegółów implementacji aplikacji serwera. Umożliwia kontenerowi akceptowanie elementów utworzonych przez dowolny serwer bez konieczności definiowania typów serwerów, z którymi może współpracować. W związku z tym użytkownik aplikacji kontenera może korzystać z przyszłych aplikacji i formatów danych. Jeśli te nowe aplikacje są składnikami OLE, dokument złożony będzie mógł dołączyć elementy utworzone przez te aplikacje.

## <a name="see-also"></a>Zobacz też

[Tło OLE](ole-background.md)<br/>
[Tło OLE: implementacja MFC](ole-background-mfc-implementation.md)<br/>
[Containers](containers.md)<br/>
[Serwery](servers.md)<br/>
[Kontenery: elementy klienta](containers-client-items.md)<br/>
[Serwery: elementy serwera](servers-server-items.md)
