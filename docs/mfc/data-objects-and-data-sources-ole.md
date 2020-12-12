---
description: 'Dowiedz się więcej na temat: obiekty danych i źródła danych (OLE)'
title: Obiekty danych i źródła danych (OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
ms.openlocfilehash: 719053e2a75b18fbf54440403351198acc66b9d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291210"
---
# <a name="data-objects-and-data-sources-ole"></a>Obiekty danych i źródła danych (OLE)

Gdy wykonujesz transfer danych przy użyciu Schowka lub przeciągając i upuść, dane mają źródło i miejsce docelowe. Jedna aplikacja udostępnia dane do skopiowania, a inna aplikacja akceptuje ją podczas wklejania. Po każdej stronie transferu trzeba wykonać różne operacje na tych samych danych, aby przeniesienie zakończyło się pomyślnie. Biblioteka Microsoft Foundation Class (MFC) zawiera dwie klasy, które reprezentują każdą ze stron tego transferu:

- Źródła danych (zgodnie z implementacją `COleDataSource` obiektów) reprezentują Źródło transferu danych. Są one tworzone przez aplikację źródłową, gdy dane mają zostać skopiowane do schowka, lub gdy dane są dostarczane dla operacji przeciągania i upuszczania.

- Obiekty danych (zgodnie z implementacją `COleDataObject` obiektów) reprezentują miejsce docelowe transferu danych. Są one tworzone, gdy do aplikacji docelowej znajdują się dane, lub gdy zostanie wyświetlony monit o wykonanie operacji wklejenia ze schowka.

W poniższych artykułach wyjaśniono, jak używać obiektów danych i źródeł danych w aplikacjach. Te informacje dotyczą zarówno aplikacji kontenera, jak i serwera, ponieważ obie mogą być wywoływane z chwilą w celu kopiowania i wklejania danych.

- [Obiekty danych i źródła danych: Tworzenie i niszczenie](data-objects-and-data-sources-creation-and-destruction.md)

- [Obiekty danych i źródła danych: manipulowanie](data-objects-and-data-sources-manipulation.md)

## <a name="in-this-section"></a>W tej sekcji

[Przeciągnij i opuść](drag-and-drop-ole.md)

[Schowek](clipboard.md)

## <a name="see-also"></a>Zobacz też

[OLE](ole-in-mfc.md)<br/>
[Klasa COleDataObject](reference/coledataobject-class.md)<br/>
[Klasa by uzyskać COleDataSource](reference/coledatasource-class.md)
