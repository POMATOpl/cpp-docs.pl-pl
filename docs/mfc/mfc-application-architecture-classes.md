---
title: Klasy architektury aplikacji Microsoft Foundation Classes (MFC)
description: Omówienie klas architektury aplikacji biblioteki Microsoft Foundation Class (MFC).
ms.date: 12/08/2020
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.openlocfilehash: 65aa9707d361c6d014c67c0f9ff1af86e19087de
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933199"
---
# <a name="mfc-application-architecture-classes"></a>Klasy związane z architekturą aplikacji MFC

Klasy Microsoft Foundation Class Library (MFC) w tej kategorii współtworzą architekturę aplikacji MFC. Dostarczają one funkcje wspólne dla większości aplikacji. Aby dodać funkcje specyficzne dla aplikacji, należy wypełnić strukturę. Zazwyczaj należy to zrobić, wprowadzając nowe klasy z klas architektury, a następnie dodając nowe składowe lub zastępując istniejące funkcje składowe.

[Kreatory aplikacji](reference/mfc-application-wizard.md) generują kilka typów aplikacji, z których wszystkie używają struktury aplikacji w różny sposób. Aplikacje SDI (Single Document Interface) i MDI (wiele dokumentów interfejsu dokumentu) umożliwiają pełne korzystanie z części dokumentu/widoku struktury. Inne typy aplikacji, takie jak aplikacje oparte na oknach dialogowych, aplikacje oparte na formularzach i biblioteki DLL, wykorzystują tylko niektóre funkcje architektury dokumentu/widoku.

Aplikacje dokumentu/widoku zawierają jeden lub więcej zestawów dokumentów, widoków i okien ramowych. Obiekt szablonu dokumentu kojarzy klasy dla każdego dokumentu/widoku/zestawu ramek.

Nie trzeba używać architektury dokumentu/widoku w aplikacji MFC, ale istnieje wiele zalet. Obsługa kontenera i serwera OLE MFC jest oparta na architekturze dokumentów/widoków, co jest obsługiwane w przypadku drukowania i podglądu wydruku.

Wszystkie aplikacje MFC mają co najmniej dwa obiekty: obiekt aplikacji pochodzący z [`CWinApp`](reference/cwinapp-class.md) , a niektóre sortowanie obiektu głównego okna, pochodne (często pośrednio) z [`CWnd`](reference/cwnd-class.md) . (Najczęściej okno główne pochodzi od [`CFrameWnd`](reference/cframewnd-class.md) , [`CMDIFrameWnd`](reference/cmdiframewnd-class.md) , lub [`CDialog`](reference/cdialog-class.md) , z których wszystkie pochodzą z `CWnd` .)

Aplikacje korzystające z architektury dokumentu/widoku zawierają dodatkowe obiekty. Główne obiekty to:

- Obiekt aplikacji pochodzący z klasy [`CWinApp`](reference/cwinapp-class.md) , jak wspomniano wcześniej.
- Jeden lub więcej obiektów klasy dokumentu pochodnych od klasy [`CDocument`](reference/cdocument-class.md) . Obiekty klasy dokumentu są odpowiedzialne za wewnętrzną reprezentację danych, które są manipulowane w widoku. Mogą być skojarzone z plikiem danych.
- Jeden lub więcej obiektów widoku pochodnych od klasy [`CView`](reference/cview-class.md) . Każdy widok to okno dołączone do dokumentu i powiązane z oknem ramki. W widokach są wyświetlane dane zawarte w obiekcie klasy dokumentu i manipulowanie nimi.

Aplikacje dokumentu/widoku zawierają również okna ramowe (pochodne od [`CFrameWnd`](reference/cframewnd-class.md) ) i szablony dokumentów (pochodzące z [`CDocTemplate`](reference/cdoctemplate-class.md) ).

## <a name="see-also"></a>Zobacz też

[Przegląd klas](class-library-overview.md)