---
description: 'Dowiedz się więcej o: serwery: elementy serwera'
title: 'Serwery: elementy serwera'
ms.date: 11/04/2016
helpviewer_keywords:
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
ms.openlocfilehash: e3fceb3abe89ca6cda432d60441a47fc0d452cfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217318"
---
# <a name="servers-server-items"></a>Serwery: elementy serwera

Gdy kontener uruchamia serwer, aby użytkownik mógł edytować osadzony lub połączony element OLE, aplikacja serwera tworzy "element serwera". Element serwera, który jest obiektem klasy pochodzącej od `COleServerItem` , udostępnia interfejs między dokumentem serwera a aplikacją kontenera.

`COleServerItem`Klasa definiuje kilka funkcji składowych, które są wywoływane przez OLE, zazwyczaj w odpowiedzi na żądania z kontenera. Elementy serwera mogą reprezentować część dokumentu serwera lub całego dokumentu. Gdy element OLE jest osadzony w dokumencie kontenera, element serwera reprezentuje cały dokument serwera. Gdy element OLE jest połączony, element serwera może reprezentować część dokumentu serwera lub cały dokument, w zależności od tego, czy łącze należy do części czy do całości.

W przykładzie [HIERSVR](../overview/visual-cpp-samples.md) , na przykład Klasa elementu serwera, `CServerItem` ma element członkowski, który jest wskaźnikiem do obiektu klasy `CServerNode` . `CServerNode`Obiekt jest węzłem w dokumencie aplikacji HIERSVR, który jest drzewem. Gdy `CServerNode` obiekt jest węzłem głównym, `CServerItem` obiekt reprezentuje cały dokument. Gdy `CServerNode` obiekt jest węzłem podrzędnym, `CServerItem` obiekt reprezentuje część dokumentu. Zapoznaj się z przykładową [HIERSVR](../overview/visual-cpp-samples.md) MFC OLE przykład.

## <a name="implementing-server-items"></a><a name="_core_implementing_server_items"></a> Implementowanie elementów serwera

Jeśli używasz Kreatora aplikacji do tworzenia kodu "Starter" dla aplikacji, wszystkie czynności, które należy wykonać, aby uwzględnić elementy serwera w początkowym kodzie, należy wybrać jedną z opcji serwera na stronie Opcje OLE. Jeśli dodajesz elementy serwera do istniejącej aplikacji, wykonaj następujące czynności:

#### <a name="to-implement-a-server-item"></a>Aby zaimplementować element serwera

1. Utwórz klasę z `COleServerItem` .

1. W klasie pochodnej Przesłoń `OnDraw` funkcję członkowską.

   Struktura wywołuje `OnDraw` , aby renderować element OLE w metaplik. Aplikacja kontenera używa tego metapliku do renderowania elementu. Klasa widoku aplikacji ma również `OnDraw` funkcję członkowską, która jest używana do renderowania elementu, gdy aplikacja serwera jest aktywna.

1. Zaimplementuj przesłonięcie `OnGetEmbeddedItem` dla klasy serwera-dokumentu. Aby uzyskać więcej informacji, zobacz artykuły [serwery: implementowanie dokumentów serwera](../mfc/servers-implementing-server-documents.md) i przykład OLE MFC [HIERSVR](../overview/visual-cpp-samples.md).

1. Zaimplementuj `OnGetExtent` funkcję członkowską klasy elementu serwera. Struktura wywołuje tę funkcję, aby pobrać rozmiar elementu. Domyślna implementacja nie robi nic.

## <a name="a-tip-for-server-item-architecture"></a><a name="_core_a_tip_for_server.2d.item_architecture"></a> Porada dotycząca architektury Server-Item

Jak wskazano w [zaimplementowaniu elementów serwera](#_core_implementing_server_items), aplikacje serwera muszą być w stanie renderować elementy zarówno w widoku serwera, jak i w metapliku używanym przez aplikację kontenera. W architekturze aplikacji biblioteka MFC, `OnDraw` funkcja członkowska klasy widoku renderuje element podczas edytowania (zobacz [CView:: OnDraw](../mfc/reference/cview-class.md#ondraw) w *odwołaniu do biblioteki klas*). Element serwera `OnDraw` renderuje element do metapliku we wszystkich innych przypadkach (zobacz [COleServerItem:: OnDraw](../mfc/reference/coleserveritem-class.md#ondraw)).

Można uniknąć duplikowania kodu przez zapisanie funkcji pomocnika w klasie dokumentu serwera i wywołanie ich z `OnDraw` funkcji w widoku i klasach elementów serwera. Przykład MFC OLE [HIERSVR](../overview/visual-cpp-samples.md) używa tej strategii: funkcje `CServerView::OnDraw` i `CServerItem::OnDraw` oba wywołania `CServerDoc::DrawTree` w celu renderowania elementu.

Widok i element mają `OnDraw` funkcje członkowskie, ponieważ są one rysowane w różnych warunkach. Widok musi uwzględniać takie czynniki jak powiększanie, rozmiar i zakres, przycinanie i elementy interfejsu użytkownika, takie jak paski przewijania. Element serwera, z drugiej strony, zawsze rysuje cały obiekt OLE.

Aby uzyskać więcej informacji, zobacz [CView:: OnDraw](../mfc/reference/cview-class.md#ondraw), [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerItem:: OnDraw](../mfc/reference/coleserveritem-class.md#ondraw)i [COleServerDoc:: OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) w *odwołaniu do biblioteki klas*.

## <a name="see-also"></a>Zobacz też

[Serwery](../mfc/servers.md)
