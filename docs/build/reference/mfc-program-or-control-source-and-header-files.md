---
description: 'Dowiedz się więcej na temat: program MFC lub źródło kontroli i pliki nagłówkowe'
title: Program MFC lub źródło kontroli i pliki nagłówkowe
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], MFC source and header
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
ms.openlocfilehash: dfe20b2e458db72a14c9ccc78df6f481442b72b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137855"
---
# <a name="mfc-program-or-control-source-and-header-files"></a>Program MFC lub źródło kontroli i pliki nagłówkowe

Następujące pliki są tworzone podczas tworzenia projektu MFC w programie Visual Studio, w zależności od opcji wybranych dla tworzonego projektu. Na przykład projekt zawiera okno *proj*. cpp i *Projname*. h pliki tylko w przypadku utworzenia projektu lub klasy opartej na oknach dialogowych.

Wszystkie te pliki znajdują się w katalogu *Projname* , a w folderze plików nagłówkowych (pliki. h) folderu lub pliki źródłowe (pliki. cpp) w Eksplorator rozwiązań.

|Nazwa pliku|Opis|
|---------------|-----------------|
|*Projname*. h|Główny plik dołączany dla programu lub biblioteki DLL. Zawiera wszystkie symbole globalne i `#include` dyrektywy dla innych plików nagłówkowych. Dziedziczy ona `CPrjnameApp` klasy z `CWinApp` i deklaruje `InitInstance` funkcję członkowską. Dla formantu, Klasa pochodzi `CPrjnameApp` od `COleControlModule` .|
|*Projname*. cpp|Główny plik źródłowy programu. Tworzy jeden obiekt klasy `CPrjnameApp` , który pochodzi od `CWinApp` i przesłania `InitInstance` funkcję członkowską.<br /><br /> W przypadku plików wykonywalnych program `CPrjnameApp::InitInstance` wykonuje kilka czynności. Rejestruje szablony dokumentów, które stanowią połączenie między dokumentami i widokami; tworzy główne okno ramek; i tworzy pusty dokument (lub otwiera dokument, jeśli jest określony jako argument wiersza polecenia dla aplikacji).<br /><br /> W przypadku bibliotek DLL i kontrolek ActiveX (dawniej OLE) program `CProjNameApp::InitInstance` rejestruje fabrykę obiektów kontrolki za pomocą OLE przez wywołanie `COleObjectFactory::RegisterAll` i wywołuje wywołanie `AfxOLEInit` . Ponadto funkcja członkowska `CProjNameApp::ExitInstance` służy do zwalniania kontroli z pamięci z wywołaniem do **AfxOleTerm**.<br /><br /> Ten plik również rejestruje i wyrejestrowuje formant w bazie danych rejestracji systemu Windows przez implementację `DllRegisterServer` `DllUnregisterServer` funkcji i.|
|*Projname* Ctrl. h, *Projname* Ctrl. cpp|Zadeklaruj i zaimplementuj `CProjnameCtrl` klasę. `CProjnameCtrl` jest pochodną `COleControl` i szkieletową implementacją niektórych funkcji Członkowskich są zdefiniowane, które inicjują, rysują i serializować (Ładuj i zapisuj) formant. Zdefiniowane są również mapy komunikatów, zdarzeń i wysyłek.|
|*Projname* okno. cpp, *Projname*. h|Utworzone w przypadku wybrania aplikacji opartej na oknach dialogowych. Pliki uzyskują i implementują klasę okna dialogowego o nazwie `CProjnameDlg` i zawierają szkieletowe funkcje składowe umożliwiające zainicjowanie okna dialogowego i przeprowadzenie wymiany danych w oknie dialogowym (DDX). Klasa okna dialogowego Informacje jest również umieszczana w tych plikach zamiast w *Projname*. cpp.|
|Dlgproxy. cpp, Dlgproxy. h|W programie opartym na oknach, implementacja i plik nagłówka dla klasy serwera proxy automatyzacji projektu dla głównego okna dialogowego. Jest on używany tylko w przypadku wybrania obsługi automatyzacji.|
|*Projname* doc. cpp, *Projname* doc. h|Utwórz i zaimplementuj klasę dokumentu o nazwie `CProjnameDoc` i Dołącz szkieletowe funkcje członkowskie, aby zainicjować dokument, serializować (Zapisz i Załaduj) dokument i wdrożyć diagnostykę debugowania.|
|*Projname* Set. h/. cpp|Tworzony w przypadku utworzenia programu, który obsługuje bazę danych i zawiera klasę zestawu rekordów.|
|*Projname* widok. cpp, *Projname* View. h|Utwórz i zaimplementuj klasę widoku o nazwie `CProjnameView` , która jest używana do wyświetlania i drukowania danych dokumentu. `CProjnameView`Klasa pochodzi od jednej z następujących klas MFC:<br /><br />- [Elementu CEditView](../../mfc/reference/ceditview-class.md)<br />- [CFormView](../../mfc/reference/cformview-class.md)<br />- [Formularzy CRecordView](../../mfc/reference/crecordview-class.md)<br />- [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)<br />- [CTreeView](../../mfc/reference/ctreeview-class.md)<br />- [CListView](../../mfc/reference/clistview-class.md)<br />- [CRichEditView](../../mfc/reference/cricheditview-class.md)<br />- [CScrollView](../../mfc/reference/cscrollview-class.md)<br />- [CView](../../mfc/reference/cview-class.md)<br />- [CHTMLView](../../mfc/reference/chtmlview-class.md)<br />- [CHTMLEditView](../../mfc/reference/chtmleditview-class.md)<br /><br /> Klasa widoku projektu zawiera szkieletowe funkcje składowe umożliwiające narysowanie widoku i zaimplementowanie diagnostyki debugowania. Jeśli włączono obsługę drukowania, wpisy mapy komunikatów są dodawane do komunikatów poleceń drukowania, drukowania i podglądu wydruku. Te wpisy wywołują odpowiednie funkcje członkowskie w klasie widoku podstawowego.|
|*Projname* PropPage. h, *Projname* PropPage. cpp|Zadeklaruj i zaimplementuj `CProjnamePropPage` klasę. `CProjnamePropPage` jest uzyskiwany z `COlePropertyPage` i szkieletową funkcją składową, `DoDataExchange` która umożliwia wdrożenie wymiany danych i walidacji.|
|IPframe. cpp, IPframe. h|Tworzony, jeśli opcja Mini-Server lub Full-Server została wybrana na stronie **Opcje automatyzacji** Kreatora aplikacji (krok 3 z 6). Pliki uzyskują i implementują klasę okien ramowych w miejscu o nazwie **CInPlaceFrame**, która jest używana, gdy serwer jest aktywowany przez program kontenerów.|
|MainFrm. cpp, MainFrm. h|Utwórz klasę **CMainFrame** z [obiektu CFrameWnd](../../mfc/reference/cframewnd-class.md) (dla aplikacji SDI) lub [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md) (dla aplikacji MDI). Klasa **CMainFrame** obsługuje tworzenie przycisków paska narzędzi i pasek stanu, jeśli odpowiednie opcje są wybrane na stronie **Opcje aplikacji** Kreatora aplikacji (krok 4 z 6). Aby uzyskać informacje na temat korzystania z programu **CMainFrame**, zobacz [klasy Frame-Window utworzone przez Kreatora aplikacji](../../mfc/frame-window-classes-created-by-the-application-wizard.md).|
|Childfrm. cpp, childfrm. h|Utwórz klasę **CChildFrame** z [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md). Klasa **CChildFrame** jest używana dla okien ramowych dokumentu MDI. Te pliki są zawsze tworzone w przypadku wybrania opcji MDI.|

## <a name="see-also"></a>Zobacz też

[Typy plików utworzone dla projektów Visual Studio C++](file-types-created-for-visual-cpp-projects.md)<br>
[Program ATL lub źródło kontroli i pliki nagłówkowe](atl-program-or-control-source-and-header-files.md)<br>
[Projekty CLR](files-created-for-clr-projects.md)
