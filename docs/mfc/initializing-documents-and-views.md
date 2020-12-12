---
description: 'Dowiedz się więcej o: Inicjowanie dokumentów i widoków'
title: Inicjowanie dokumentów i widoków
ms.date: 11/04/2016
helpviewer_keywords:
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
ms.openlocfilehash: ea0840faefac0ae5a8b4cee0fe3b707a92737c70
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208037"
---
# <a name="initializing-documents-and-views"></a>Inicjowanie dokumentów i widoków

Dokumenty są tworzone na dwa różne sposoby, więc Klasa dokumentu musi obsługiwać oba metody. Po pierwsze użytkownik może utworzyć nowy pusty dokument z poleceniem File New. W takim przypadku zainicjuj dokument w przesłonięciu funkcji składowej [OnNewDocument](reference/cdocument-class.md#onnewdocument) klasy [CDocument](reference/cdocument-class.md). Następnie użytkownik może użyć polecenia Otwórz w menu plik, aby utworzyć nowy dokument, którego zawartość jest odczytywana z pliku. W takim przypadku zainicjuj dokument w przesłonięciu funkcji członkowskiej [OnOpenDocument](reference/cdocument-class.md#onopendocument) klasy `CDocument` . Jeśli obie inicjalizacje są takie same, można wywołać wspólną funkcję członkowską z obu zastąpień lub `OnOpenDocument` wywołać metodę `OnNewDocument` inicjowania czystego dokumentu, a następnie zakończyć operację otwierania.

Widoki są tworzone po utworzeniu dokumentów. Najlepszy czas na zainicjowanie widoku to po zakończeniu tworzenia dokumentu, okna ramki i widoku przez platformę. Możesz zainicjować widok, zastępując [OnInitialUpdate](reference/cview-class.md#oninitialupdate) funkcję członkowską [CView](reference/cview-class.md). Jeśli konieczne jest ponowne zainicjowanie lub dostosowanie wszystkich elementów przy każdej zmianie dokumentu, można przesłonić [aktualizację](reference/cview-class.md#onupdate).

## <a name="see-also"></a>Zobacz też

[Inicjowanie i oczyszczanie dokumentów i widoków](initializing-and-cleaning-up-documents-and-views.md)
