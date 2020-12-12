---
description: 'Dowiedz się więcej na temat: używanie klas do pisania aplikacji dla systemu Windows'
title: Używanie klas do pisania aplikacji dla systemu Windows
ms.date: 11/04/2016
helpviewer_keywords:
- Windows applications [MFC], MFC application framework
- MFC, application development
- applications [OLE], MFC application framework
- MFC ActiveX controls [MFC], creating
- OLE applications [MFC], MFC application framework
- database applications [MFC], creating
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
ms.openlocfilehash: b94155b565872b614efa291699cecbaf4770fdaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322715"
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>Używanie klas do pisania aplikacji dla systemu Windows

Razem klasy w bibliotece Microsoft Foundation Class (MFC) składają się na "platformę aplikacji", na której tworzysz aplikację dla systemu operacyjnego Windows. Na bardzo ogólnym poziomie struktura definiuje szkielet aplikacji i dostarcza standardowe implementacje interfejsu użytkownika, które można umieścić w sieci szkieletowej. Zadaniem programisty jest wypełnienie reszty szkieletu, które są charakterystyczne dla danej aplikacji. Możesz uzyskać początek przy użyciu Kreatora aplikacji MFC, aby utworzyć pliki dla bardzo dokładnej aplikacji początkowej. Za pomocą edytorów zasobów Microsoft Visual C++ można zaprojektować elementy interfejsu użytkownika wizualnie, Widok klasy polecenia, aby połączyć te elementy z kodem, i bibliotekę klas, aby zaimplementować logikę specyficzną dla aplikacji.

Wersja 3,0 i nowsza w ramach platformy MFC obsługuje programowanie dla platform Win32, w tym Microsoft Windows 95 i nowszych, oraz Windows NT w wersji 3,51 i nowszych. Obsługa MFC Win32 obejmuje wielowątkowość. Użyj wersji 1,5 *x* , jeśli konieczne jest programowanie 16-bitowe.

Ta rodzina artykułów przedstawia szeroki przegląd struktury aplikacji. Eksploruje również główne obiekty tworzące aplikację i sposób ich tworzenia. Wśród tematów wymienionych w poniższych artykułach są następujące:

- [Struktura](../mfc/framework-mfc.md).

- Dzielenie zawodów między platformą i kodem, zgodnie z opisem w temacie [Tworzenie na platformie](../mfc/building-on-the-framework.md).

- [Klasa aplikacji](../mfc/cwinapp-the-application-class.md), która hermetyzuje funkcje na poziomie aplikacji.

- Jak [Szablony dokumentów](../mfc/document-templates-and-the-document-view-creation-process.md) tworzą dokumenty i okna z ramkami oraz zarządzają nimi.

- Klasa [CWnd](../mfc/window-objects.md), główna Klasa podstawowa wszystkich okien.

- [Obiekty graficzne](../mfc/graphic-objects.md), takie jak pióra i pędzle.

Inne części platformy obejmują:

- [Obiekty okien: przegląd](../mfc/window-objects.md)

- [Obsługa i mapowanie komunikatów](../mfc/message-handling-and-mapping.md)

- [CObject, główna Klasa bazowa w MFC](../mfc/using-cobject.md)

- [Architektura dokumentu/widoku](../mfc/document-view-architecture.md)

- [Okna dialogowe](../mfc/dialog-boxes.md)

- [Formanty](../mfc/controls-mfc.md)

- [Paski sterowania](../mfc/control-bars.md)

- [OLE](../mfc/ole-in-mfc.md)

- [Zarządzanie pamięcią](../mfc/memory-management.md)

   Oprócz tego, że można pisać aplikacje dla systemu operacyjnego Windows, MFC ułatwia również pisanie aplikacji korzystających z funkcji łączenia i osadzania obiektów OLE. Możesz dodać aplikację do kontenera edycji wizualnej OLE, serwera edycji wizualnej wizualizacji lub obu tych elementów, aby inne aplikacje mogły korzystać z obiektów z aplikacji lub nawet zdalnie na dysku.

- [Kontrolki ActiveX MFC](../mfc/mfc-activex-controls.md)

   Zestaw narzędzi OLE Control Development Kit (CDK) jest teraz w pełni zintegrowany z platformą. Ten rodzina artykułów zawiera omówienie programowania formantów ActiveX za pomocą MFC. (Formanty ActiveX były wcześniej znane jako formanty OLE).

- [Programowanie baz danych](../data/data-access-programming-mfc-atl.md)

   MFC udostępnia również dwa zestawy klas baz danych, które upraszczają zapisywanie aplikacji dostępu do danych. Korzystając z klas baz danych ODBC, można łączyć się z bazami danych za pośrednictwem sterownika Open Database Connectivity (ODBC), wybierać rekordy z tabel i wyświetlać informacje o rekordach w formularzu na ekranie. Korzystając z klas obiektów dostępu do danych (DAO), można współpracować z bazami danych za pośrednictwem aparatu bazy danych Microsoft Jet lub zewnętrznych źródeł danych (innych niż Jet), w tym źródeł danych ODBC.

   Ponadto MFC jest w pełni włączone do pisania aplikacji, które używają zestawów znaków Unicode i wielobajtowych (MBCS), w tym zestawów znaków dwubajtowych (DBCS).

Ogólne Przewodnik dotyczący dokumentacji MFC zawiera temat ogólne informacje dotyczące [MFC](../mfc/general-mfc-topics.md).

## <a name="see-also"></a>Zobacz też

[Ogólne tematy dotyczące MFC](../mfc/general-mfc-topics.md)
