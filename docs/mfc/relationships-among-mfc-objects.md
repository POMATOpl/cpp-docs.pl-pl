---
description: Dowiedz się więcej na temat relacji między obiektami MFC
title: Relacje między obiektami MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
ms.openlocfilehash: 0646d487d1d60293461316edddcb97fde30905a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218059"
---
# <a name="relationships-among-mfc-objects"></a>Relacje między obiektami MFC

Aby ułatwić przeprowadzenie procesu tworzenia dokumentu/widoku w perspektywie, należy wziąć pod uwagę uruchomiony program: dokument, okno ramki używane do wyświetlania widoku oraz widok skojarzony z tym dokumentem.

- Dokument zachowuje listę widoków tego dokumentu oraz wskaźnik do szablonu dokumentu, który utworzył dokument.

- Widok utrzymuje wskaźnik do dokumentu i jest elementem podrzędnym okna ramki nadrzędnej.

- Okno ramki dokumentu utrzymuje wskaźnik do bieżącego aktywnego widoku.

- Szablon dokumentu przechowuje listę otwartych dokumentów.

- Aplikacja zachowuje listę szablonów dokumentów.

- System Windows śledzi wszystkie otwarte okna, aby mógł wysyłać do nich komunikaty.

Te relacje są ustanawiane podczas tworzenia dokumentu/widoku. W poniższej tabeli przedstawiono sposób, w jaki obiekty w działającym programie mogą uzyskać dostęp do innych obiektów. Każdy obiekt może uzyskać wskaźnik do obiektu aplikacji, wywołując funkcję globalną [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp).

### <a name="gaining-access-to-other-objects-in-your-application"></a>Uzyskiwanie dostępu do innych obiektów w aplikacji

|Z obiektu|Jak uzyskać dostęp do innych obiektów|
|-----------------|---------------------------------|
|Dokument|Użyj [GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) i [GetNextView](../mfc/reference/cdocument-class.md#getnextview) , aby uzyskać dostęp do listy widoku dokumentu.<br /><br /> Wywołaj [GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate) , aby pobrać szablon dokumentu.|
|Widok|Wywołaj metodę [GetDocument](../mfc/reference/cview-class.md#getdocument) , aby uzyskać dokument.<br /><br /> Wywołaj [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe) , aby pobrać okno ramki.|
|Okno ramki dokumentu|Wywołaj [GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview) , aby uzyskać bieżący widok.<br /><br /> Wywołaj [GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument) w celu pobrania dokumentu dołączonego do bieżącego widoku.|
|Okno ramek MDI|Wywołaj [MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive) , aby pobrać aktualnie aktywną [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).|

Zazwyczaj okno ramki ma jeden widok, ale czasami, jak w oknach rozdzielacza, to samo okno ramowe zawiera wiele widoków. Okno ramki utrzymuje wskaźnik do aktualnie aktywnego widoku; wskaźnik jest aktualizowany za każdym razem, gdy inny widok zostanie aktywowany.

> [!NOTE]
> Wskaźnik do okna głównego ramki jest przechowywany w zmiennej składowej [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) obiektu aplikacji. Wywołanie w ramach `OnFileNew` przesłonięcia `InitInstance` funkcji składowej `CWinApp` zestawu *m_pMainWnd* . W przypadku braku wywołania `OnFileNew` , należy ustawić wartość zmiennej we `InitInstance` własnym zakresie. (Aplikacje składnika COM interfejsu SDI (serwer) mogą nie ustawiać zmiennej, jeśli przełącznikiem/Embedding jest w wierszu polecenia.) Należy pamiętać, że *m_pMainWnd* jest teraz członkiem klasy, `CWinThread` a nie `CWinApp` .

## <a name="see-also"></a>Zobacz też

[Szablony dokumentów i proces tworzenia dokumentu/widoku](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Tworzenie szablonu dokumentu](../mfc/document-template-creation.md)<br/>
[Tworzenie dokumentu/widoku](../mfc/document-view-creation.md)<br/>
[Tworzenie nowych dokumentów, okien i widoków](../mfc/creating-new-documents-windows-and-views.md)
