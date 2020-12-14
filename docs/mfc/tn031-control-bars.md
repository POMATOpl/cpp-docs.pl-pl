---
description: 'Dowiedz się więcej na temat: TN031: paski sterowania'
title: 'TN031: paski sterowania'
ms.date: 11/04/2016
f1_keywords:
- vc.controls.bars
helpviewer_keywords:
- control bars [MFC], styles
- CStatusBar class [MFC], Tech Note 31 usage
- CControlBar class [MFC], Tech Note 31 usage
- CControlBar class [MFC], deriving from
- control bars [MFC], classes [MFC]
- CDialogBar class [MFC], Tech Note 31 usage
- CToolBar class [MFC], Tech Note 31 usage
- TN031
- styles [MFC], control bars
ms.assetid: 8cb895c0-40ea-40ef-90ee-1dd29f34cfd1
ms.openlocfilehash: 42dddf1afabdf2ab04ba8441208e7109eeacbd65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215550"
---
# <a name="tn031-control-bars"></a>TN031: paski sterowania

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga opisuje klasy pasków sterowania w MFC: ogólne [CControlBar](#_mfcnotes_ccontrolbar), [CStatusBar](#_mfcnotes_cstatusbar), [CToolBar](#_mfcnotes_ctoolbar), [CDialogBar](#_mfcnotes_cdialogbar)i `CDockBar` .

## <a name="ccontrolbar"></a><a name="_mfcnotes_ccontrolbar"></a> CControlBar

A `ControlBar` jest `CWnd` klasą pochodną, która:

- Jest wyrównany do górnej lub dolnej części okna ramki.

- Może zawierać elementy podrzędne, które są kontrolkami opartymi na elemencie HWND (na przykład `CDialogBar` ) lub `HWND` na elementach nieopartych na elemencie (na przykład, `CToolBar` `CStatusBar` ).

Paski sterowania obsługują dodatkowe style:

- CBRS_TOP (domyślnie) Przypnij pasek sterowania do góry.

- CBRS_BOTTOM przypiąć pasek kontroli do dołu.

- CBRS_NOALIGN nie zmieniaj położenia paska sterowania, gdy zmieniany jest rozmiar elementu nadrzędnego.

Klasy pochodne `CControlBar` zapewniają bardziej interesujące implementacje:

- `CStatusBar` Pasek stanu, elementy są okienkami paska stanu zawierającymi tekst.

- `CToolBar` Pasek narzędzi, elementy są przyciski mapy bitowej wyrównane w wierszu.

- `CDialogBar` Ramka przypominająca pasek narzędzi zawierająca standardowe formanty systemu Windows (utworzone na podstawie zasobu szablonu okna dialogowego).

- `CDockBar` Uogólniony obszar dokowania dla innych `CControlBar` obiektów pochodnych. Określone funkcje członkowskie i zmienne dostępne w tej klasie mogą ulec zmianie w przyszłych wydaniach.

Wszystkie obiekty pasków sterowania/okna będą oknami podrzędnymi okna niektórych klatek nadrzędnych. Są one zazwyczaj dodawane jako elementy równorzędne do obszaru klienckiego ramki (na przykład klienta MDI lub widoku). Identyfikator okna podrzędnego paska sterowania jest ważny. Domyślny układ paska sterowania działa tylko dla pasków sterowania z identyfikatorami w zakresie AFX_IDW_CONTROLBAR_FIRST do AFX_IDW_CONTROLBAR_LAST. Należy pamiętać, że mimo że istnieje zakres identyfikatorów słupków kontrolnych 256, pierwsze 32 tych identyfikatorów słupków kontrolnych są specyficzne, ponieważ są one bezpośrednio obsługiwane przez architekturę podglądu wydruku.

`CControlBar`Klasa zapewnia standardową implementację:

- Wyrównywanie paska sterowania do góry, do dołu lub po obu stronach ramki.

- Alokowanie tablic elementów kontroli.

- Obsługa implementacji klas pochodnych.

Obiekty słupków kontrolnych języka C++ są zwykle osadzane jako elementy członkowskie `CFrameWnd` klasy pochodnej i zostaną oczyszczone po `HWND` zniszczeniu elementu nadrzędnego i obiektu. Jeśli zachodzi potrzeba przydzielenia obiektu paska sterowania na stercie, można po prostu ustawić dla elementu członkowskiego *M_bAutoDestruct* **wartość true** , aby pasek sterowania został **usunięty**, gdy `HWND` zostanie zniszczony.

> [!NOTE]
> Jeśli utworzysz własną `CControlBar` klasę pochodną, zamiast korzystać z jednej z klas pochodnych MFC, takich jak `CStatusBar` , `CToolBar` , lub `CDialogBar` , musisz ustawić element członkowski danych *m_dwStyle* . Można to zrobić w przesłonięciu `Create` :

```
// CMyControlBar is derived from CControlBar
BOOL CMyControlBar::Create(CWnd* pParentWnd,
    DWORD dwStyle,
    UINT nID)
{
    m_dwStyle = dwStyle;

.
.
.
}
```

**Algorytm układu paska sterowania**

Algorytm układu paska sterowania jest bardzo prosty. Okno ramki wysyła komunikat WM_SIZEPARENT do wszystkich elementów podrzędnych w zakresie paska sterowania. Wraz z tym komunikatem jest przenoszona wskaźnik do prostokąta klienta elementu nadrzędnego. Ta wiadomość jest wysyłana do elementów podrzędnych w kolejności Z. Elementy podrzędne na pasku sterowania używają tych informacji do pozycjonowania i zmniejszania rozmiaru obszaru klienckiego elementu nadrzędnego. Końcowy prostokąt pozostawiony dla normalnego obszaru klienta (mniejsze paski kontroli) służy do określenia głównego okna klienta (zazwyczaj jest to klient MDI, widok lub okno rozdzielacza).

Zobacz `CWnd::RepositionBars` i, `CFrameWnd::RecalcLayout` Aby uzyskać więcej szczegółów.

Prywatne komunikaty systemu Windows z systemem MFC, w tym WM_SIZEPARENT, są udokumentowane w [uwadze technicznej 24](../mfc/tn024-mfc-defined-messages-and-resources.md).

## <a name="cstatusbar"></a><a name="_mfcnotes_cstatusbar"></a> CStatusBar

Pasek stanu jest paskiem sterowania, który ma wiersz okienka tekstu wyjściowego. Istnieją dwa typowe sposoby używania okienek wyjściowych tekstu:

- Jako wiersz wiadomości

     (na przykład standardowy wiersz wiadomości pomocy). Są one zazwyczaj używane przez indeksowane na podstawie 0

- Jako wskaźniki stanu

     (na przykład wskaźniki zakończenia, NUM i SCRL). Są one zazwyczaj używane przez ciąg/identyfikator polecenia.

Czcionka paska stanu to 10-punktowy MS Sans Serif (podyktowany przez przewodnik projektowania aplikacji interfejsu systemu Windows lub mapowania czcionek najlepiej dopasowane do 10-punktowej szwajcarskiej czcionki proporcjonalnej). W niektórych wersjach systemu Windows, takich jak wersja japońska, czcionki wybrane są różne.

Kolory używane na pasku stanu są również spójne z zaleceniem przewodnika projektowania aplikacji interfejsu systemu Windows. Te kolory nie są twarde i są zmieniane dynamicznie w odpowiedzi na dostosowanie użytkownika w panelu sterowania.

|Element|Wartość koloru systemu Windows|Domyślny RGB|
|----------|-------------------------|-----------------|
|Tło paska stanu|COLOR_BTNFACE|RGB (192, 192, 192)|
|Tekst paska stanu|COLOR_BTNTEXT|RGB (000, 000 ITD.)|
|Górny/lewy brzeg paska stanu|COLOR_BTNHIGHLIGHT|RGB (255, 255, 255)|
|Pasek stanu bot/prawej krawędzi|COLOR_BTNSHADOW|RGB (128, 128, 128)|

**Obsługa usługi CCmdUI dla CStatusBar**

Sposób, w jaki wskaźniki są zwykle aktualizowane, odbywa się za pomocą mechanizmu ON_UPDATE_COMMAND_UI. W czasie bezczynności pasek stanu wywoła procedurę obsługi ON_UPDATE_COMMAND_UI z IDENTYFIKATORem ciągu okienka wskaźnika.

Procedura obsługi ON_UPDATE_COMMAND_UI może wywoływać:

- `Enable`: Aby włączyć lub wyłączyć okienko. Wyłączone okienko wygląda tak samo jak włączone okienko, ale tekst jest niewidoczny (oznacza to, że wyłącza wskaźnik tekstu).

- `SetText`: Aby zmienić tekst. Należy zachować ostrożność, jeśli używasz tego, ponieważ nie zmieni się rozmiar okienka automatycznie.

Aby uzyskać szczegółowe informacje na temat tworzenia i interfejsów API dostosowywania, zapoznaj się z klasą [CStatusBar](../mfc/reference/cstatusbar-class.md) w *dokumentacji biblioteki klas* `CStatusBar` . Większość dostosowania słupków stanu należy wykonać, zanim pasek stanu jest początkowo widoczny.

Pasek stanu obsługuje tylko jedno okienko rozciągania, zazwyczaj pierwsze okienko. Rozmiar tego okienka jest w rzeczywistości minimalny. Jeśli pasek stanu jest większy niż minimalny rozmiar wszystkich okienek, w okienku rozciągania zostanie nadana dodatkowa szerokość. Aplikacja domyślna z paskiem stanu ma wskaźniki wyrównane do prawej dla CAP, NUM i SCRL, ponieważ pierwsze okienko jest rozciągane.

## <a name="ctoolbar"></a><a name="_mfcnotes_ctoolbar"></a> CToolBar

Pasek narzędzi jest paskiem sterowania z wierszem przycisków mapy bitowej, które mogą zawierać separatory. Obsługiwane są dwa style przycisków: przyciski i pola wyboru. Funkcje grupy radia można skompilować przy użyciu przycisków pól wyboru i ON_UPDATE_COMMAND_UI.

Wszystkie przyciski mapy bitowej na pasku narzędzi są pobierane z jednej mapy bitowej. Ta mapa bitowa musi zawierać jeden obraz lub symbol dla każdego przycisku. Zazwyczaj kolejność obrazów/symboli w mapie bitowej jest taka sama jak kolejność, w jakiej są rysowane na ekranie. (Można to zmienić za pomocą interfejsów API dostosowywania).

Każdy przycisk musi mieć ten sam rozmiar. Wartość domyślna to standardowe 24x22 pikseli. Każdy obraz/symbol musi mieć ten sam rozmiar i musi być umieszczony obok siebie w mapie bitowej. Domyślny rozmiar obrazu/glifu to 16x15 pikseli. W związku z tym na pasku narzędzi z 10 przyciskami (przy użyciu standardowych rozmiarów) potrzebna jest mapa bitowa o rozmiarze 160 pikseli i o szerokości 15 pikseli.

Każdy przycisk ma jeden i tylko jeden obraz/symbol. Różne stany przycisku i style (na przykład naciśnięto, w górę, w dół, wyłączone, wyłączone, nieokreślony) są algorithmically generowane na podstawie tego jednego obrazu/glifu. Każda mapa bitowa koloru lub DIB może być używana teoretycznie. Algorytm generowania różnych stanów przycisków działa najlepiej, jeśli oryginalny obraz jest odcieniami szarości. Zapoznaj się ze standardowymi przyciskami paska narzędzi i przyciskiem paska narzędzi, który znajduje się w ogólnym [przykładzie biblioteki](../overview/visual-cpp-samples.md) MFC.

Kolory używane na pasku narzędzi są również spójne z zaleceniem przewodnika projektowania aplikacji interfejsu systemu Windows. Te kolory nie są twarde i są zmieniane dynamicznie w odpowiedzi na dostosowanie użytkownika w panelu sterowania.

|Element|Wartość koloru systemu Windows|Domyślny RGB|
|----------|-------------------------|-----------------|
|Tło paska narzędzi|COLOR_BTNFACE|RGB (192192192)|
|Przyciski paska narzędzi w górnej/lewej krawędzi|COLOR_BTNHIGHLIGHT|RGB (255255255)|
|Przyciski paska narzędzi bot/prawej krawędzi|COLOR_BTNSHADOW|RGB (128128128)|

Ponadto przyciski mapy bitowej paska narzędzi są ponownie kolorem, tak jakby były standardowymi kontrolkami przycisków systemu Windows. To Ponowne kolorowanie występuje, gdy mapa bitowa zostanie załadowana z zasobu i w odpowiedzi na zmianę kolorów systemowych w odpowiedzi na dostosowanie użytkownika w panelu sterowania. Następujące kolory w mapie bitowej paska narzędzi zostaną automatycznie odkolorowe, więc powinny być używane z zachowaniem ostrożności. Jeśli nie chcesz, aby część mapy bitowej była kolorem, Użyj koloru, który dokładnie przybliża jedną z zamapowanych wartości RGB. Mapowanie jest wykonywane na podstawie dokładnych wartości RGB.

|Wartość RGB|Dynamicznie zamapowana wartość koloru|
|---------------|------------------------------------|
|RGB (000, 000 ITD.)|COLOR_BTNTEXT|
|RGB (128, 128, 128)|COLOR_BTNSHADOW|
|RGB (192, 192, 192)|COLOR_BTNFACE|
|RGB (255, 255, 255)|COLOR_BTNHIGHLIGHT|

*Aby uzyskać szczegółowe* informacje o interfejsach API tworzenia i dostosowywania, zapoznaj się z klasą [CToolBar](../mfc/reference/ctoolbar-class.md) `CToolBar` . Większość przygotowań pasków narzędzi należy wykonać, zanim pasek narzędzi zostanie początkowo widoczny.

Interfejsy API dostosowywania mogą służyć do dostosowywania identyfikatorów przycisków, stylów, szerokości odstępów oraz tego, który obraz/symbol jest używany dla tego przycisku. Domyślnie nie trzeba używać tych interfejsów API.

## <a name="ccmdui-support-for-ctoolbar"></a>Obsługa usługi CCmdUI dla CToolBar

Sposób, w jaki przyciski paska narzędzi są zawsze aktualizowane, odbywa się za pomocą mechanizmu ON_UPDATE_COMMAND_UI. W czasie bezczynności pasek narzędzi wywoła procedurę obsługi ON_UPDATE_COMMAND_UI z IDENTYFIKATORem polecenia tego przycisku. ON_UPDATE_COMMAND_UI nie jest wywoływana dla separatorów, ale jest wywoływana dla przycisków przycisku i pola wyboru.

Procedura obsługi ON_UPDATE_COMMAND_UI może wywoływać:

- `Enable`: Aby włączyć lub wyłączyć przycisk. Działa tak samo, jak przyciski i pola wyboru.

- `SetCheck`: Aby ustawić stan zaznaczenia przycisku. Wywołanie tej opcji dla przycisku paska narzędzi spowoduje przekształcenie go w przycisk pola wyboru. `SetCheck` przyjmuje parametr, który może mieć wartość 0 (nie sprawdzono), 1 (zaznaczone) lub 2 (nieokreślone)

- `SetRadio`: Skrót dla `SetCheck` .

Przyciski pola wyboru są przyciskami pola wyboru "Auto"; oznacza to, że po naciśnięciu przez użytkownika natychmiast zmieni stan. Zaznaczony jest stan w dół lub w dół. Nie ma wbudowanego interfejsu użytkownika, aby zmienić przycisk w stan "nieokreślony"; należy to zrobić przez kod.

Interfejsy API dostosowywania umożliwiają zmianę stanu danego przycisku paska narzędzi, najlepiej należy zmienić te stany w obsłudze ON_UPDATE_COMMAND_UI dla polecenia, które reprezentuje przycisk paska narzędzi. Należy pamiętać, że przetwarzanie bezczynne zmieni stan przycisków paska narzędzi za pomocą procedury obsługi ON_UPDATE_COMMAND_UI, więc wszelkie zmiany wprowadzone za pomocą przycisku SetButton mogą zostać utracone po następnym bezczynności.

Przyciski paska narzędzi będą wysyłać WM_COMMAND komunikaty, takie jak normalne przyciski lub elementy menu, i są zwykle obsługiwane przez procedurę obsługi ON_COMMAND w tej samej klasie, która udostępnia procedurę obsługi ON_UPDATE_COMMAND_UI.

Istnieją cztery style przycisków paska narzędzi (wartości TBBS_) używane do wyświetlania stanów:

- TBBS_CHECKED: pole wyboru jest aktualnie zaznaczone (w dół).

- TBBS_INDETERMINATE: pole wyboru jest obecnie nieokreślone.

- TBBS_DISABLED: przycisk jest obecnie wyłączony.

- TBBS_PRESSED: przycisk jest obecnie wciśnięty.

Sześć oficjalnych opcji podręcznika projektowania aplikacji interfejsu systemu Windows są reprezentowane przez następujące wartości TBBS:

- W górę = 0

- Mysz w dół = TBBS_PRESSED (&#124; dowolny inny styl)

- Wyłączone = TBBS_DISABLED

- Dół = TBBS_CHECKED

- Wyłączony: TBBS_CHECKED &#124; TBBS_DISABLED

- Nieokreślone = TBBS_INDETERMINATE

## <a name="cdialogbar"></a><a name="_mfcnotes_cdialogbar"></a> CDialogBar

Pasek okna dialogowego jest paskiem sterowania, który zawiera standardowe formanty systemu Windows. Działa jak okno dialogowe, w którym znajduje się kontrolki i obsługuje tabulację między nimi. Działa również jak okno dialogowe, w którym jest używane szablon okna dialogowego do reprezentowania paska.

`CDialogBar`Jest używany dla paska narzędzi Drukowanie podglądu, który zawiera standardowe kontrolki przycisków.

Użycie elementu przypomina `CDialogBar` użycie `CFormView` . Należy zdefiniować szablon okna dialogowego i usunąć wszystkie style, z wyjątkiem WS_CHILD. Należy zauważyć, że okno dialogowe nie może być widoczne.

Powiadomienia o kontrolkach dla a `CDialogBar` będą wysyłane do elementu nadrzędnego na pasku sterowania (podobnie jak przyciski paska narzędzi).

## <a name="ccmdui-support-for-cdialogbar"></a>Obsługa usługi CCmdUI dla CDialogBar

Przyciski paska dialogowego należy zaktualizować za pomocą mechanizmu obsługi ON_UPDATE_COMMAND_UI. W czasie bezczynności pasek okna dialogowego wywoła procedurę obsługi ON_UPDATE_COMMAND_UI z IDENTYFIKATORem polecenia wszystkich przycisków o IDENTYFIKATORze >= 0x8000 (czyli w zakresie identyfikatorów poleceń).

Procedura obsługi ON_UPDATE_COMMAND_UI może wywoływać:

- Włącz: Aby włączyć lub wyłączyć przycisk.

- SetText: Aby zmienić tekst przycisku.

Dostosowanie można wykonać za poorednictwem standardowych interfejsów API Menedżera okien.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
