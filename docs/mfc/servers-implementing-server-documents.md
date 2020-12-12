---
description: 'Dowiedz się więcej o programie: serwery: implementowanie dokumentów serwera'
title: 'Serwery: implementowanie dokumentów serwera'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
ms.openlocfilehash: b8843d3e2ac662cbb018a3063c9f04f5dd8d6f10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217331"
---
# <a name="servers-implementing-server-documents"></a>Serwery: implementowanie dokumentów serwera

W tym artykule opisano kroki, które należy wykonać w celu pomyślnego zaimplementowania dokumentu serwera, jeśli nie określono opcji serwer OLE w Kreatorze aplikacji.

#### <a name="to-define-a-server-document-class"></a>Aby zdefiniować klasę dokumentu serwera

1. Utwórz klasę dokumentu od `COleServerDoc` zamiast `CDocument` .

1. Utwórz klasę elementu serwera pochodną `COleServerItem` .

1. Zaimplementuj `OnGetEmbeddedItem` funkcję członkowską klasy dokumentu serwera.

   `OnGetEmbeddedItem` jest wywoływana, gdy użytkownik aplikacji kontenera tworzy lub edytuje element osadzony. Powinien zwrócić element reprezentujący cały dokument. Powinien to być obiekt `COleServerItem` klasy pochodnej.

1. Zastąp `Serialize` funkcję członkowską, aby serializować zawartość dokumentu. Nie trzeba serializować listy elementów serwera, chyba że są używane do reprezentowania danych natywnych w dokumencie. Aby uzyskać więcej informacji, zobacz *implementowanie elementów serwera* w artykule [serwery: elementy serwera](../mfc/servers-server-items.md).

Po utworzeniu dokumentu na serwerze struktura automatycznie rejestruje dokument przy użyciu bibliotek DLL systemu OLE. Dzięki temu biblioteki DLL mogą identyfikować dokumenty serwera.

Aby uzyskać więcej informacji, zobacz [COleServerItem](../mfc/reference/coleserveritem-class.md) i [COleServerDoc](../mfc/reference/coleserverdoc-class.md) w *dokumentacji biblioteki klas*.

## <a name="see-also"></a>Zobacz też

[Serwery](../mfc/servers.md)<br/>
[Serwery: elementy serwera](../mfc/servers-server-items.md)<br/>
[Serwery: implementowanie serwera](../mfc/servers-implementing-a-server.md)<br/>
[Serwery: implementowanie okien ramowych In-Place](../mfc/servers-implementing-in-place-frame-windows.md)
