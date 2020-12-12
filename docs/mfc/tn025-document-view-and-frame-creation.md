---
description: 'Dowiedz się więcej na temat: TN025: Tworzenie dokumentów, widoków i ramek'
title: 'TN025: tworzenie dokumentów, widoków i ramek'
ms.date: 11/04/2016
f1_keywords:
- vc.creation
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
ms.openlocfilehash: 034c3670df57de03cf7db8f713937f3d433fbb56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215745"
---
# <a name="tn025-document-view-and-frame-creation"></a>TN025: tworzenie dokumentów, widoków i ramek

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga opisuje problemy z tworzeniem i własnością dla WinApps, DocTemplates, dokumentów, ramek i widoków.

## <a name="winapp"></a>WinApp

`CWinApp`W systemie istnieje jeden obiekt.

Jest on statycznie skonstruowany i zainicjowany przez wewnętrzną implementację struktury `WinMain` . Należy `CWinApp` wykonać od do do nic przydatne (wyjątek: biblioteki DLL rozszerzenia MFC nie powinny mieć `CWinApp` wystąpienia — Inicjalizacja jest wykonywana w `DllMain` zamian).

Ten `CWinApp` obiekt jest właścicielem listy szablonów dokumentów (a `CPtrList` ). Istnieje co najmniej jeden szablon dokumentu dla aplikacji. DocTemplates są zwykle ładowane z pliku zasobów (czyli tablicy ciągów) w `CWinApp::InitInstance` .

```
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);

AddDocTemplate(pTemplate);
```

Jeden `CWinApp` obiekt jest właścicielem wszystkich okien ramowych w aplikacji. Główne okno ramek dla aplikacji powinno być przechowywane w programie `CWinApp::m_pMainWnd` ; zwykle ustawiasz *m_pMainWnd* w implementacji, `InitInstance` Jeśli nie zezwolisz AppWizard na to za Ciebie. W przypadku interfejsu pojedynczego dokumentu (SDI) jest to ten `CFrameWnd` , który służy jako główne okno ramek aplikacji, a także okno ramki dokumentu. W przypadku interfejsu wielu dokumentów (MDI) jest to MDI-Frame (Klasa `CMDIFrameWnd` ), która służy jako okno głównej ramki aplikacji, które zawiera wszystkie elementy podrzędne `CFrameWnd` . Każde okno podrzędne jest klasy `CMDIChildWnd` (pochodzące od `CFrameWnd` ) i służy jako jeden z potencjalnie wielu okien ramowych dokumentu.

## <a name="doctemplates"></a>DocTemplates

`CDocTemplate`Jest twórcą i menedżerem dokumentów. Jest właścicielem tworzonych przez niego dokumentów. Jeśli aplikacja używa metody opartej na zasobach opisanej poniżej, nie musi ona pochodzić od `CDocTemplate` .

W przypadku aplikacji SDI Klasa `CSingleDocTemplate` śledzi jeden otwarty dokument. W przypadku aplikacji MDI Klasa `CMultiDocTemplate` przechowuje listę `CPtrList` wszystkich aktualnie otwartych dokumentów utworzonych na podstawie tego szablonu. `CDocTemplate::AddDocument` i `CDocTemplate::RemoveDocument` udostępniaj wirtualne funkcje członkowskie do dodawania lub usuwania dokumentu z szablonu. `CDocTemplate` jest znajomym `CDocument` , aby można było ustawić chroniony `CDocument::m_pDocTemplate` wskaźnik wstecz, aby wskazywał szablon dokumentu, który utworzył dokument.

`CWinApp` obsługuje `OnFileOpen` implementację domyślną, co spowoduje wykonanie zapytania względem wszystkich szablonów doc. Implementacja obejmuje już otwarte dokumenty i decydowanie o formacie, w którym mają być otwierane nowe dokumenty.

`CDocTemplate` zarządza wiązaniem interfejsu użytkownika dla dokumentów i ramek.

`CDocTemplate` zachowuje liczbę nienazwanych dokumentów.

## <a name="cdocument"></a>CDocument

A `CDocument` jest własnością `CDocTemplate` .

Dokumenty mają listę obecnie otwartych widoków (pochodzących z `CView` ), które wyświetlają dokument (a `CPtrList` ).

Dokumenty nie tworzą/niszczyją widoków, ale są po nich połączone. Gdy dokument zostanie zamknięty (oznacza to, że za pomocą pliku/zamknięcia) wszystkie dołączone widoki zostaną zamknięte. Gdy ostatni widok w dokumencie zostanie zamknięty (oznacza to, że okno/zamknięcie), dokument zostanie zamknięty.

`CDocument::AddView` `RemoveView` Interfejs jest używany do obsługi listy widoku. `CDocument` jest znajomym `CView` , aby można było ustawić `CView::m_pDocument` wskaźnik tyłu.

## <a name="cframewnd"></a>CFrameWnd

A `CFrameWnd` (znany również jako ramka) odgrywa tę samą rolę jak w MFC 1,0, ale teraz `CFrameWnd` Klasa jest przeznaczona do użycia w wielu przypadkach bez wyznaczania nowej klasy. Klasy pochodne `CMDIFrameWnd` i `CMDIChildWnd` są również udoskonalone tak, aby wiele poleceń standardowych zostało już zaimplementowanych.

`CFrameWnd`Jest odpowiedzialny za tworzenie okien w obszarze klienta ramki. Zwykle jest jedno okno główne wypełniające obszar klienta ramki.

W przypadku okna MDI-Frame obszar klienta jest wypełniany kontrolką MDICLIENT, która jest z kolei elementem nadrzędnym wszystkich okien ramowych MDI-Child. W przypadku okna SDI-Frame lub okna ramki MDI-Child, obszar klienta jest zwykle wypełniany `CView` obiektem okna pochodnego. W przypadku `CSplitterWnd` , obszar klienta widoku jest wypełniany przy użyciu `CSplitterWnd` obiektu okna, a `CView` obiekty okien pochodnych (po jednym dla okienka podzielonego) są tworzone jako podrzędne okna `CSplitterWnd` .

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
