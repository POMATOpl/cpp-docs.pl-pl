---
description: 'Dowiedz się więcej o programie: korzystanie z dokumentów'
title: Używanie dokumentów
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
ms.openlocfilehash: 486604733808fb027d6dd0fbf81bb670c85313f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154503"
---
# <a name="using-documents"></a>Używanie dokumentów

Współpraca, dokumenty i widoki:

- Zawierają i wyświetlaj [dane](../mfc/managing-data-with-document-data-variables.md)specyficzne dla aplikacji oraz zarządzaj nimi.

- Podaj interfejs składający się z [zmiennych danych dokumentu](../mfc/managing-data-with-document-data-variables.md) do manipulowania danymi.

- Uczestnictwo w [pisaniu i odczytywaniu plików](../mfc/serializing-data-to-and-from-files.md).

- Uczestnictwo w [drukowaniu](../mfc/role-of-the-view-in-printing.md).

- [Obsługa](../mfc/handling-commands-in-the-document.md) większości poleceń i komunikatów aplikacji.

Dokument jest szczególnie związany z zarządzaniem danymi. Przechowuj dane, zwykle w zmiennych składowych klasy dokumentu. Widok używa tych zmiennych do uzyskiwania dostępu do danych do wyświetlania i aktualizowania. Domyślny mechanizm serializacji dokumentu zarządza odczytami i zapisywaniem danych do i z plików. Dokumenty mogą również obsługiwać polecenia (ale nie komunikaty systemu Windows inne niż WM_COMMAND).

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Wyprowadzanie klasy dokumentów z obiektu CDocument](../mfc/deriving-a-document-class-from-cdocument.md)

- [Zarządzanie danymi za pomocą zmiennych danych dokumentu](../mfc/managing-data-with-document-data-variables.md)

- [Serializacja danych do plików i z plików](../mfc/serializing-data-to-and-from-files.md)

- [Pomijanie mechanizmu serializacji](../mfc/bypassing-the-serialization-mechanism.md)

- [Obsługa poleceń w dokumencie](../mfc/handling-commands-in-the-document.md)

- [Funkcja członkowska OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument)

- [Funkcja członkowska DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)

## <a name="see-also"></a>Zobacz też

[Architektura dokumentu/widoku](../mfc/document-view-architecture.md)
