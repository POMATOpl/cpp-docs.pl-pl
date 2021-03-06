---
description: 'Dowiedz się więcej na temat: Tworzenie dokumentu/widoku'
title: Tworzenie Document-View
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], creating
- views [MFC], and frame windows
- views [MFC], creating
- tables [MFC]
- MFC, views
- document/view architecture [MFC], creating document/view
- object creators
- MFC, documents
- tables [MFC], objects each MFC object creates
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
ms.openlocfilehash: 128b68eb53bd596ba2e4b4df4f2c5e865452fe2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326438"
---
# <a name="documentview-creation"></a>Tworzenie dokumentu/widoku

Struktura dostarcza implementacje **nowych** i **otwartych** poleceń (między innymi) w menu **plik** . Tworzenie nowego dokumentu wraz z jego skojarzonym widokiem i oknem ramki to wspólne wysiłki między obiektem aplikacji, szablonem dokumentu, nowo utworzonym dokumentem i nowo utworzonym oknem ramki. Poniższa tabela zawiera podsumowanie obiektów, które należy utworzyć.

### <a name="object-creators"></a>Twórcy obiektów

|Kreator|Tworzy|
|-------------|-------------|
|Obiekt aplikacji|Szablon dokumentu|
|Szablon dokumentu|Dokument|
|Szablon dokumentu|Okno ramowe|
|Okno ramowe|Widok|

## <a name="see-also"></a>Zobacz też

[Szablony dokumentów i proces tworzenia dokumentu/widoku](document-templates-and-the-document-view-creation-process.md)<br/>
[Tworzenie szablonu dokumentu](document-template-creation.md)<br/>
[Relacje między obiektami MFC](relationships-among-mfc-objects.md)<br/>
[Tworzenie nowych dokumentów, okien i widoków](creating-new-documents-windows-and-views.md)
