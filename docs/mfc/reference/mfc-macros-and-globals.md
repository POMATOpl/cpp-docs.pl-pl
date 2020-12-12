---
description: 'Dowiedz się więcej na temat: makra MFC i Globals'
title: Makra i funkcje globalne MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions [MFC]
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
ms.openlocfilehash: 9e3d3acd74d1cf6db5856432cdefd632e36185f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219151"
---
# <a name="mfc-macros-and-globals"></a>Makra i funkcje globalne MFC

Biblioteka MFC można podzielić na dwie główne sekcje: (1) klasy MFC i (2) makra i Globals. Jeśli funkcja lub zmienna nie jest elementem członkowskim klasy, jest to funkcja globalna lub zmienna.

Biblioteki MFC i Active Template Library (ATL) dzielą makra konwersji ciągu. Aby uzyskać więcej informacji, zobacz [makra konwersji ciągów](../../atl/reference/string-conversion-macros.md) w dokumentacji ATL.

Makra MFC i funkcje oferty Globals w następujących kategoriach.

## <a name="general-mfc"></a>Ogólna MFC

- [Typy danych](data-types-mfc.md)

- [Rzutowanie typów obiektów klas MFC](type-casting-of-mfc-class-objects.md)

- [Usługi modelu obiektów czasu wykonywania](run-time-object-model-services.md)

- [Usługi diagnostyczne](diagnostic-services.md)

- [Przetwarzanie wyjątków](exception-processing.md)

- [Formatowanie obiektu CString i wyświetlanie okna komunikatu](cstring-formatting-and-message-box-display.md)

- [Mapy komunikatów](message-map-macros-mfc.md)

- [Mapowania delegatów i interfejsów](delegate-and-interface-maps.md)

- [Moduły i biblioteki DLL](extension-dll-macros.md)

- [Informacje o aplikacji i zarządzanie nią](application-information-and-management.md)

- [Identyfikatory poleceń standardowych i okien](standard-command-and-window-ids.md)

- [Pomocnicy klasy kolekcji](collection-class-helpers.md)

- [Funkcje szarych i symulowanych map bitowych](gray-and-dithered-bitmap-functions.md)

- [Standardowe procedury wymiany danych w oknie dialogowym (DDX)](standard-dialog-data-exchange-routines.md)

- [Standardowe procedury walidacji danych (DDV) okna dialogowego](standard-dialog-data-validation-routines.md)

- [Komunikaty AFX](afx-messages.md)

- [Style formantu ToolBar](toolbar-control-styles.md)

- [CMFCImagePaintArea:: IMAGE_EDIT_MODE, Wyliczenie](cmfcimagepaintarea-image-edit-mode-enumeration.md)

## <a name="database"></a>baza danych

- [Funkcje wymiany pól rekordów (RFX)](record-field-exchange-functions.md) i [Funkcje wymiany zbiorczych pól rekordów (bulk RFX)](record-field-exchange-functions.md) dla klas MFC ODBC

- [Funkcje wymiany pól rekordów (DFX)](record-field-exchange-functions.md) dla klas MFC DAO

- [Funkcje wymiany danych okna dialogowego (DDX) dla formularzy CRecordView i CDaoRecordView](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (klasy MFC ODBC i DAO)

- [Funkcje wymiany danych okna dialogowego (DDX) dla kontrolek OLE](dialog-data-exchange-functions-for-ole-controls.md)

- [Makra i Globals do pomocy w wywołaniu funkcji interfejsu API Open Database Connectivity (ODBC) bezpośrednio](database-macros-and-globals.md)

- [Inicjowanie i kończenie działania aparatu bazy danych DAO](dao-database-engine-initialization-and-termination.md)

## <a name="internet"></a>Internet

- [Funkcje globalne do analizowania internetowych adresów URL](internet-url-parsing-globals.md)

## <a name="dhtml--dhtml-event-maps"></a>Mapy zdarzeń DHTML/DHTML

- [Makra pomocnika wymiany danych w formacie DHTML (DDX)](ddx-dhtml-helper-macros.md)

- [Mapy zdarzeń DHTML](dhtml-event-maps.md)

## <a name="ole"></a>OLE

- [Inicjowanie OLE](ole-initialization.md)

- [Kontrola aplikacji](application-control.md)

- [Mapy wysyłania](dispatch-maps.md)

Ponadto MFC udostępnia funkcję o nazwie [AfxEnableControlContainer —](ole-initialization.md#afxenablecontrolcontainer) , która umożliwia każdy kontener OLE opracowany z MFC 4,0 do pełnej obsługi osadzonych kontrolek OLE.

## <a name="ole-controls"></a>Formanty OLE

- [Stałe typów parametru Variant](variant-parameter-type-constants.md)

- [Dostęp do biblioteki typów](type-library-access.md)

- [Strony właściwości](property-pages-mfc.md)

- [Mapy zdarzeń](event-maps.md)

- [Mapy wychwytywania zdarzeń](event-sink-maps.md)

- [Mapy połączeń](connection-maps.md)

- [Rejestrowanie kontrolek OLE](registering-ole-controls.md)

- [Fabryki klas i licencjonowanie](class-factories-and-licensing.md)

- [Stan trwały kontrolek OLE](persistence-of-ole-controls.md)

W pierwszej części tej sekcji omówiono wszystkie poprzednie kategorie i listę Globals i makr w kategorii wraz z krótkimi opisami funkcji. Poniżej przedstawiono opisy funkcji globalnych, zmiennych globalnych i makr w bibliotece MFC.

> [!NOTE]
> Wiele funkcji globalnych zaczyna się od prefiksu "AFX", ale niektóre z nich, na przykład funkcje wymiany danych okna dialogowego (DDX) i wiele funkcji bazy danych, nie są zgodne z tą konwencją. Wszystkie zmienne globalne zaczynają się od "AFX" jako prefiksu. Makra nie zaczynają się żadnym określonym prefiksem, ale są pisane wielkimi literami.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../mfc/class-library-overview.md)
