---
description: 'Dowiedz się więcej na temat: klasy widoków (architektura)'
title: Klasy widoków (architektura)
ms.date: 09/17/2019
helpviewer_keywords:
- form and record views [MFC]
- view classes [MFC]
- control views [MFC]
- view classes [MFC], architecture
ms.assetid: 8894579a-1436-441e-b985-83711061e495
ms.openlocfilehash: fe883c34ad8bd3948ee65ecec25151cc4dd2416c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143133"
---
# <a name="view-classes-architecture"></a>Klasy widoków (architektura)

`CView` i jej klasy pochodne są oknami podrzędnymi, które reprezentują obszar klienta okna ramki. Widoki wyświetlają dane i akceptują dane wejściowe dla dokumentu.

Klasa widoku jest skojarzona z klasą dokumentu i klasą okna ramowego przy użyciu obiektu szablonu dokumentu.

[CView](../mfc/reference/cview-class.md)<br/>
Klasa bazowa dla widoków specyficznych dla aplikacji w danych dokumentu. Wyświetla dane i akceptują dane wejściowe użytkownika w celu edytowania lub zaznaczania danych. Utwórz klasy widoków z `CView` .

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
Klasa bazowa dla widoków z możliwościami przewijania. Utwórz klasę widoku od `CScrollView` do automatycznego przewijania.

## <a name="form-and-record-views"></a>Widoki formularzy i rekordów

Widoki formularzy są również przewijane. Są one oparte na szablonie okna dialogowego.

Widoki rekordów są wyprowadzane z widoków formularza. Oprócz szablonu okna dialogowego mają także połączenie z bazą danych.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Widok przewijania, którego układ jest zdefiniowany w szablonie okna dialogowego. Utwórz klasę z `CFormView` , aby zaimplementować interfejs użytkownika w oparciu o szablon okna dialogowego.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Udostępnia widok formularza bezpośrednio połączony z obiektem zestawu rekordów obiektu dostępu do danych (DAO). Podobnie jak w przypadku wszystkich widoków formularzy, `CDaoRecordView` jest oparty na szablonie okna dialogowego. Obiekty DAO są używane z bazami danych programu Access i są obsługiwane za pomocą pakietu Office 2013. Element DAO 3,6 jest wersją ostateczną i jest uznawany za przestarzały.

[CHtmlView](../mfc/reference/chtmlview-class.md)<br/>
Obsługuje kontrolkę przeglądania sieci Web w aplikacji. Kontrolka obsługuje dynamiczny kod HTML w MFC.

[COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)<br/>
Zapewnia obsługę OLE DB MFC w widokach formularzy.

[Formularzy CRecordView](../mfc/reference/crecordview-class.md)<br/>
Udostępnia widok formularza połączony bezpośrednio z obiektem zestawu rekordów Open Database Connectivity (ODBC). Podobnie jak w przypadku wszystkich widoków formularzy, `CRecordView` jest oparty na szablonie okna dialogowego.

## <a name="control-views"></a>Widoki formantów

Widoki formantów wyświetlają formant jako widok.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Klasa bazowa dla wszystkich widoków skojarzonych z kontrolkami systemu Windows. Poniżej opisano widoki oparte na kontrolkach.

[Elementu CEditView](../mfc/reference/ceditview-class.md)<br/>
Widok, który zawiera kontrolkę edycji standardowej systemu Windows (zobacz [CEdit](../mfc/reference/cedit-class.md)). Kontrolki edycji obsługują edytowanie tekstu, wyszukiwanie, zastępowanie i przewijanie.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Widok, który zawiera kontrolkę zaawansowanej edycji systemu Windows (zobacz [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Oprócz możliwości kontrolki edycji, formanty edycji wzbogaconej obsługują czcionki, kolory, formatowanie akapitu i osadzone obiekty OLE.

[CListView](../mfc/reference/clistview-class.md)<br/>
Widok zawierający formant listy systemu Windows (zobacz [CListCtrl](../mfc/reference/clistctrl-class.md)). Kontrolka listy wyświetla ikony i ciągi w sposób podobny do prawego okienka Eksploratora plików.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Widok, który zawiera kontrolkę drzewa systemu Windows (zobacz [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Kontrolka drzewa wyświetla ikony i ciągi uporządkowane w hierarchii w sposób podobny do lewego okienka Eksploratora plików.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../mfc/class-library-overview.md)
