---
description: 'Dowiedz się więcej na temat: klasy przeciągania i upuszczania OLE oraz Transfer danych'
title: Klasy przeciągania i upuszczania oraz transferów danych OLE
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
ms.openlocfilehash: ea19efd05fe4b85a5c0e2ff57412f7eb1d05fcfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244111"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>Klasy przeciągania i upuszczania oraz transferów danych OLE

Te klasy są używane w transferach danych OLE. Umożliwiają one przesyłanie danych między aplikacjami przy użyciu Schowka lub poprzez przeciąganie i upuszczanie.

[COleDropSource](reference/coledropsource-class.md)<br/>
Steruje operacją przeciągania i upuszczania od początku do końca. Ta klasa określa, kiedy rozpocznie się operacja przeciągania, a po jej zakończeniu. Wyświetla również informacje zwrotne kursora podczas operacji przeciągania i upuszczania.

[By uzyskać COleDataSource](reference/coledatasource-class.md)<br/>
Używany, gdy aplikacja udostępnia dane do transferu danych. `COleDataSource` może być przeglądany jako obiekt schowka zorientowany obiektowo.

[COleDropTarget](reference/coledroptarget-class.md)<br/>
Reprezentuje element docelowy operacji przeciągania i upuszczania. `COleDropTarget`Obiekt odpowiada okno na ekranie. Określa, czy zatwierdzić wszystkie dane, które zostały na nim usunięte, i implementuje rzeczywistą operację usuwania.

[COleDataObject](reference/coledataobject-class.md)<br/>
Używane jako strona odbiornika `COleDataSource` . `COleDataObject` obiekty zapewniają dostęp do danych przechowywanych przez `COleDataSource` obiekt.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](class-library-overview.md)
