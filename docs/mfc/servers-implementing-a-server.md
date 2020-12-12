---
description: 'Dowiedz się więcej o programie: serwery: implementowanie serwera'
title: 'Serwery: implementowanie serwera'
ms.date: 11/04/2016
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
ms.openlocfilehash: 3ced10f88ce062ab571841610ba4b000571835b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217383"
---
# <a name="servers-implementing-a-server"></a>Serwery: implementowanie serwera

W tym artykule opisano kod, który Kreator aplikacji MFC tworzy dla aplikacji serwera edycji wizualnej. Jeśli nie używasz Kreatora aplikacji, w tym artykule wymieniono obszary, w których należy napisać kod w celu zaimplementowania aplikacji serwera.

Jeśli tworzysz nową aplikację serwerową za pomocą Kreatora aplikacji, zapewnia ona znaczną ilość kodu specyficznego dla serwera. Jeśli dodajesz funkcje serwera Visual Editing do istniejącej aplikacji, musisz zduplikować kod, który Kreator aplikacji udostępnił przed dodaniem pozostałej części niezbędnego kodu serwera.

Kod serwera, który zawiera Kreator aplikacji, znajduje się w kilku kategoriach:

- Definiowanie zasobów serwera:

  - Zasób menu używany, gdy serwer programu edytuje element osadzony w osobnym oknie.

  - Zasoby menu i paska narzędzi używane, gdy serwer jest aktywny.

  Aby uzyskać więcej informacji na temat tych zasobów, zobacz [menu i zasoby: Dodatki do serwera](../mfc/menus-and-resources-server-additions.md).

- Definiowanie klasy elementu pochodzącej od `COleServerItem` . Aby uzyskać więcej informacji na temat elementów serwera, zobacz [serwery: elementy serwera](../mfc/servers-server-items.md).

- Zmiana klasy bazowej klasy dokumentu na `COleServerDoc` . Aby uzyskać więcej informacji, zobacz [serwery: implementowanie dokumentów serwera](../mfc/servers-implementing-server-documents.md).

- Definiowanie klasy okna ramowego pochodnego od `COleIPFrameWnd` . Aby uzyskać więcej informacji, zobacz [serwery: implementowanie okien ramowych In-Place](../mfc/servers-implementing-in-place-frame-windows.md).

- Tworzenie wpisu dla aplikacji serwerowej w bazie danych rejestracji systemu Windows i rejestrowanie nowego wystąpienia serwera przy użyciu systemu OLE. Aby uzyskać informacje na temat tego tematu, zobacz [rejestracja](../mfc/registration.md).

- Inicjowanie i uruchamianie aplikacji serwera. Aby uzyskać informacje na temat tego tematu, zobacz [rejestracja](../mfc/registration.md).

Aby uzyskać więcej informacji, zobacz [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerDoc](../mfc/reference/coleserverdoc-class.md)i [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) w *dokumentacji biblioteki klas*.

## <a name="see-also"></a>Zobacz też

[Serwery](../mfc/servers.md)<br/>
[Containers](../mfc/containers.md)<br/>
[Menu i zasoby (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Rejestracja](../mfc/registration.md)
