---
description: 'Dowiedz się więcej na temat: klasy dokumentów i widoków tworzone przez Kreatora aplikacji MFC'
title: Klasy dokumentów i widoków tworzone przez kreatora aplikacji MFC
ms.date: 11/04/2016
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
ms.openlocfilehash: f182278ebdd971364e3e35e15e51b6ea5e7aaf68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330308"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>Klasy dokumentów i widoków tworzone przez kreatora aplikacji MFC

Kreator aplikacji MFC umożliwia rozpoczęcie pracy nad programowaniem programu, tworząc w ten sposób klasy sieci szkieletowej i widoku. Następnie można [mapować polecenia i komunikaty do tych klas](reference/mapping-messages-to-functions.md) , a następnie używać edytora kodu źródłowego Visual C++ do pisania funkcji składowych.

Klasa dokumentu utworzona przez Kreatora aplikacji MFC jest pochodną klasy [CDocument](reference/cdocument-class.md). Klasa widoku pochodzi od [CView](reference/cview-class.md). Nazwy, które Kreator aplikacji udostępniają te klasy, i pliki, które je zawierają, są zależne od nazwy projektu podawanej w oknie dialogowym Kreator aplikacji. W Kreatorze aplikacji można użyć strony wygenerowane klasy, aby zmienić domyślne nazwy.

Niektóre aplikacje mogą potrzebować więcej niż jednej klasy dokumentu, klasy widoku lub klasy okien ramowych. Aby uzyskać więcej informacji, zobacz [wiele typów dokumentów, widoków i okien ramowych](multiple-document-types-views-and-frame-windows.md).

## <a name="see-also"></a>Zobacz też

[Architektura dokumentu/widoku](document-view-architecture.md)
