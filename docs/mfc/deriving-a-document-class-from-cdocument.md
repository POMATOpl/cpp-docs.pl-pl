---
description: 'Dowiedz się więcej na temat: wyprowadzanie klasy dokumentu z CDocument'
title: Wyprowadzanie klasy dokumentów z obiektu CDocument
ms.date: 11/04/2016
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
ms.openlocfilehash: 9f6dccb5400ba0e62b2f11a3c2d4074cb9bb2f25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327887"
---
# <a name="deriving-a-document-class-from-cdocument"></a>Wyprowadzanie klasy dokumentów z obiektu CDocument

Dokumenty zawierają dane aplikacji i zarządzają nimi. Aby użyć klasy dokumentu dostarczonej przez Kreatora aplikacji MFC, należy wykonać następujące czynności:

- Utwórz klasę `CDocument` dla każdego typu dokumentu.

- Dodaj Zmienne Członkowskie do przechowywania danych poszczególnych dokumentów.

- Przesłoń `CDocument` `Serialize` funkcję członkowską w klasie dokumentu. `Serialize` zapisuje i odczytuje dane dokumentu z i z dysku.

## <a name="other-document-functions-often-overridden"></a>Inne funkcje dokumentu są często zastępowane

Możesz również chcieć przesłonić inne `CDocument` funkcje składowe. W szczególności często trzeba przesłonić [OnNewDocument](reference/cdocument-class.md#onnewdocument) i [OnOpenDocument](reference/cdocument-class.md#onopendocument) , aby zainicjować składowe danych dokumentu i [DeleteContents](reference/cdocument-class.md#deletecontents) , aby zniszczyć dynamiczne przydzielane dane. Aby uzyskać informacje na temat składowych, zobacz Klasa [CDocument](reference/cdocument-class.md) w *dokumentacji MFC*.

## <a name="see-also"></a>Zobacz też

[Używanie dokumentów](using-documents.md)
