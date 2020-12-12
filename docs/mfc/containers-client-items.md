---
description: 'Dowiedz się więcej o: Containers: elementy klienta'
title: 'Kontenery: elementy klienckie'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
ms.openlocfilehash: e8aff84e825723b1615a0dbbadf7d5fec6d4cef1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310437"
---
# <a name="containers-client-items"></a>Kontenery: elementy klienckie

W tym artykule wyjaśniono, czym są elementy klienta i od jakich klas aplikacja powinna dziedziczyć elementy klienta.

Elementy klienta to elementy danych należące do innej aplikacji, które są zawarte w dokumencie lub do którego odwołuje się aplikacja kontenera OLE. Elementy klienta, których dane znajdują się w dokumencie, są osadzone; te, których dane są przechowywane w innej lokalizacji, do której odwołuje się dokument kontenera, są połączone.

Klasa dokumentu w aplikacji OLE pochodzi od klasy [COleDocument](reference/coledocument-class.md) , a nie z `CDocument` . `COleDocument`Klasa dziedziczy ze `CDocument` wszystkich funkcji niezbędnych do korzystania z architektury dokumentu/widoku, na których oparto aplikacje MFC. `COleDocument` definiuje również interfejs, który traktuje dokument jako kolekcję `CDocItem` obiektów. `COleDocument`Do dodawania, pobierania i usuwania elementów tej kolekcji są udostępniane kilka funkcji Członkowskich.

Każda aplikacja kontenera powinna dziedziczyć co najmniej jedną klasę od `COleClientItem` . Obiekty tej klasy reprezentują elementy, osadzone lub połączone, w dokumencie OLE. Te obiekty istnieją w okresie istnienia dokumentu zawierającego je, chyba że zostaną usunięte z dokumentu.

`CDocItem` jest klasą bazową dla `COleClientItem` i `COleServerItem` . Obiekty klas pochodzących od tych dwóch działań jako pośredników między elementem OLE a aplikacjami klienta i serwera. Za każdym razem, gdy nowy element OLE zostanie dodany do dokumentu, struktura MFC dodaje nowy obiekt klasy pochodnej aplikacji klienckiej `COleClientItem` do kolekcji `CDocItem` obiektów dokumentu.

## <a name="see-also"></a>Zobacz też

[Containers](containers.md)<br/>
[Kontenery: pliki złożone](containers-compound-files.md)<br/>
[Kontenery: problemy z User-Interface](containers-user-interface-issues.md)<br/>
[Kontenery: funkcje zaawansowane](containers-advanced-features.md)<br/>
[Klasa COleClientItem](reference/coleclientitem-class.md)<br/>
[Klasa COleServerItem](reference/coleserveritem-class.md)
