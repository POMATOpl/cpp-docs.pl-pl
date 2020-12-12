---
description: 'Dowiedz się więcej o: TN062: odbicie komunikatu dla formantów systemu Windows'
title: 'TN062: odbicie komunikatu dla formantów systemu Windows'
ms.date: 06/28/2018
f1_keywords:
- vc.controls.messages
helpviewer_keywords:
- ON_WM_VKEYTOITEM_REFLECT macro [MFC]
- ON_WM_DRAWITEM_REFLECT macro [MFC]
- ON_WM_VSCROLL_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT message [MFC]
- ON_CONTROL_REFLECT_EX macro [MFC]
- ON_UPDATE_COMMAND_UI_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT_EX message [MFC]
- ON_WM_HSCROLL_REFLECT macro [MFC]
- message reflection [MFC]
- ON_WM_COMPAREITEM_REFLECT macro [MFC]
- ON_WM_MEASUREITEM_REFLECT macro [MFC]
- ON_NOTIFY message [MFC]
- WM_COMMAND [MFC]
- WM_CTLCOLOR message [MFC]
- TN062 [MFC]
- ON_WM_CHARTOITEM_REFLECT macro [MFC]
- ON_WM_CTLCOLOR_REFLECT macro [MFC]
- ON_WM_DELETEITEM_REFLECT macro [MFC]
- notification messages [MFC]
- ON_WM_PARENTNOTIFY_REFLECT macro [MFC]
- WM_NOTIFY message [MFC]
- ON_CONTROL_REFLECT macro
ms.assetid: 53efb0ba-fcda-4fa0-a3c7-14e0b78fb494
ms.openlocfilehash: 9dc106c1513032e654acfc2c4b86b8eb3b939578
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214731"
---
# <a name="tn062-message-reflection-for-windows-controls"></a>TN062: odbicie komunikatu dla formantów systemu Windows

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga techniczna opisuje odbicie komunikatów i nową funkcję w MFC 4,0. Zawiera również wskazówki dotyczące tworzenia prostej kontroli wielokrotnego użytku, która używa odbicia komunikatów.

Ta Uwaga techniczna nie omawia odbicia komunikatu, ponieważ ma zastosowanie do kontrolek ActiveX (wcześniej nazywanych kontrolkami OLE). Zapoznaj się z artykułem [formanty ActiveX: Tworzenie podklasy kontrolki systemu Windows](../mfc/mfc-activex-controls-subclassing-a-windows-control.md).

**Co to jest odbicie komunikatu**

Formanty systemu Windows często wysyłają komunikaty powiadomień do okien nadrzędnych. Na przykład wiele kontrolek wysyła komunikat z powiadomieniem o kolorze kontrolki (WM_CTLCOLOR lub jeden z jego wariantów) do ich elementów nadrzędnych, aby umożliwić nadrzędnemu podaniu pędzla do rysowania tła.

W systemie Windows i w MFC przed wersją 4,0 okno nadrzędne, często jest oknem dialogowym, jest odpowiedzialne za obsługę tych komunikatów. Oznacza to, że kod do obsługi wiadomości musi znajdować się w klasie okna nadrzędnego i musi być zduplikowany w każdej klasie, która musi obsługiwać ten komunikat. W przypadku powyżej każde okno dialogowe, które chciało kontrolować z tłem niestandardowym, będzie musiało obsługiwać komunikat z powiadomieniem o kolorze kontrolki. Wielokrotne ponowne użycie kodu będzie znacznie łatwiejsze, jeśli można napisać klasę kontrolki, która mogłaby obsłużyć własny kolor tła.

W MFC 4,0, stary mechanizm nadal działa — okna nadrzędne mogą obsługiwać komunikaty powiadomień. Ponadto MFC 4,0 ułatwia ponowne użycie przez udostępnienie funkcji o nazwie "odbicie komunikatów", która umożliwia obsługę tych komunikatów powiadomień w oknie kontroli podrzędnej lub w oknie nadrzędnym albo w obu. W przykładzie koloru tła formantu można teraz napisać klasę kontrolki, która ustawia swój własny kolor tła, obsługując odbicie WM_CTLCOLOR wiadomości, bez polegania na elemencie nadrzędnym. (Należy zauważyć, że ponieważ odbicie komunikatów jest implementowane przez MFC, a nie przez Windows, Klasa okna nadrzędnego musi pochodzić z, aby `CWnd` odbicie komunikatu działało.)

Starsze wersje MFC miały coś podobnego do odbicia komunikatów przez udostępnienie funkcji wirtualnych dla kilku komunikatów, takich jak komunikaty dla pól listy rysowanych przez właściciela (WM_DRAWITEM itd.). Nowy mechanizm odbicia komunikatów jest uogólniony i spójny.

Odbicie komunikatu jest zgodne z kodem zapisanym dla wersji MFC przed 4,0.

Jeśli podano procedurę obsługi dla określonej wiadomości lub dla zakresu komunikatów w klasie okna nadrzędnego, przesłonisz obsługę komunikatów odbitych dla tego samego komunikatu, pod warunkiem, że funkcja obsługi klasy bazowej nie zostanie wywołana we własnym obsłudze. Na przykład jeśli obsłużysz WM_CTLCOLOR w klasie okna dialogowego, obsługa przesłoni wszystkie odbite procedury obsługi komunikatów.

Jeśli w klasie okna nadrzędnego podasz procedurę obsługi dla określonego komunikatu WM_NOTIFY lub zakres komunikatów WM_NOTIFY, procedura obsługi zostanie wywołana tylko wtedy, gdy kontrolka podrzędna wysyłająca te komunikaty nie ma obsługiwanego przez program obsługi komunikatów `ON_NOTIFY_REFLECT()` . Jeśli używasz `ON_NOTIFY_REFLECT_EX()` na mapie wiadomości, program obsługi komunikatów może lub nie zezwalać na działanie okna nadrzędnego do obsługi wiadomości. Jeśli program obsługi zwróci **wartość false**, komunikat zostanie również obsłużony przez element nadrzędny, a wywołanie zwracające **wartość true** nie zezwala na działanie elementu nadrzędnego. Zwróć uwagę, że komunikat odbity jest obsługiwany przed komunikatem powiadomienia.

Po wysłaniu wiadomości WM_NOTIFY formant jest oferowany jako pierwsza szansa na jego obsługę. W przypadku wysłania innej wiadomości odbitej okno nadrzędne będzie miało pierwszą szansę na jego obsługę, a kontrolka odbierze komunikat o odbiciu. W tym celu będzie potrzebna funkcja obsługi i odpowiedni wpis na mapie komunikatów klasy kontrolki.

Makro mapy komunikatów dla komunikatów odbitych jest nieco inne niż w przypadku zwykłych powiadomień: *_REFLECT* dołączone do nazwy zwyczajowej. Na przykład aby obsłużyć WM_NOTIFY komunikatu w obiekcie nadrzędnym, należy użyć makra ON_NOTIFY na mapie wiadomości elementu nadrzędnego. Aby obsłużyć odbicie komunikatu w formancie podrzędnym, użyj makra ON_NOTIFY_REFLECT w mapie komunikatów formantu podrzędnego. W niektórych przypadkach parametry są również inne. Należy pamiętać, że ClassWizard może zwykle dodawać wpisy mapy komunikatów dla Ciebie i dostarczać implementacje funkcji szkieletowej z prawidłowymi parametrami.

Zobacz [TN061: ON_NOTIFY i WM_NOTIFY messages](../mfc/tn061-on-notify-and-wm-notify-messages.md) , aby uzyskać informacje o nowym WM_NOTIFY komunikacie.

**Wpisy mapy komunikatów i prototypy funkcji obsługi dla wiadomości odbitej**

Aby obsłużyć komunikat z powiadomieniem o przekazaniu kontroli, użyj makr mapy komunikatów i prototypów funkcji wymienionych w poniższej tabeli.

ClassWizard mogą zwykle dodawać te wpisy mapy komunikatów dla użytkownika i dostarczać implementacje funkcji szkieletowej. Aby uzyskać informacje na temat sposobu definiowania programów obsługi komunikatów, zobacz [Definiowanie obsługi komunikatów dla wiadomości odbitej](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) .

Aby przeprowadzić konwersję z nazwy komunikatu do nazwy makra odzwierciedlonego, poprzedź *ON_* i Dołącz *_REFLECT*. Na przykład WM_CTLCOLOR jest ON_WM_CTLCOLOR_REFLECT. (Aby zobaczyć, które wiadomości można odzwierciedlić, wykonaj odwrotną konwersję wpisów makr w poniższej tabeli).

Powyższe trzy wyjątki od reguły są następujące:

- Makro WM_COMMAND powiadomień jest ON_CONTROL_REFLECT.

- Makro dla WM_NOTIFY odbicia jest ON_NOTIFY_REFLECT.

- Makro dla ON_UPDATE_COMMAND_UI odbicia jest ON_UPDATE_COMMAND_UI_REFLECT.

W każdym z powyższych specjalnych przypadków należy określić nazwę funkcji elementu członkowskiego programu obsługi. W innych przypadkach należy użyć standardowej nazwy dla funkcji obsługi.

Znaczenie parametrów i wartości zwracanych funkcji są udokumentowane jako nazwa funkcji lub nazwa funkcji z *włączonym* prefiksem. Na przykład `CtlColor` jest udokumentowana w `OnCtlColor` . Kilka obsłudze komunikatów odbitych wymaga mniejszej liczby parametrów niż podobne procedury obsługi w oknie nadrzędnym. W poniższej tabeli są zgodne z nazwami parametrów formalnych w dokumentacji.

|Wpis mapy|Prototyp funkcji|
|---------------|------------------------|
|**ON_CONTROL_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **( );**|
|**ON_NOTIFY_REFLECT (** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **(NMHDR** <strong>\*</strong> `pNotifyStruct` **, LRESULT** <strong>\*</strong> *wynik* **);**|
|**ON_UPDATE_COMMAND_UI_REFLECT (** `memberFxn` **)**|**afx_msg void** `memberFxn` **(CCmdUI** <strong>\*</strong> `pCmdUI` **);**|
|**ON_WM_CTLCOLOR_REFLECT ()**|**AFX_MSG HBRUSH CtlColor (** <strong>\*</strong> `pDC` przechwytywanie zmian **, Uint** `nCtlColor` **);**|
|**ON_WM_DRAWITEM_REFLECT ()**|**afx_msg void DrawItem (LPDRAWITEMSTRUCT** `lpDrawItemStruct` **);**|
|**ON_WM_MEASUREITEM_REFLECT ()**|**afx_msg void MeasureItem (LPMEASUREITEMSTRUCT** `lpMeasureItemStruct` **);**|
|**ON_WM_DELETEITEM_REFLECT ()**|**afx_msg void DeleteItem (LPDELETEITEMSTRUCT** `lpDeleteItemStruct` **);**|
|**ON_WM_COMPAREITEM_REFLECT ()**|**afx_msg int CompareItem (LPCOMPAREITEMSTRUCT** `lpCompareItemStruct` **);**|
|**ON_WM_CHARTOITEM_REFLECT ()**|**afx_msg int CharToItem (uint** `nKey` **, uint** `nIndex` **);**|
|**ON_WM_VKEYTOITEM_REFLECT ()**|**afx_msg int VKeyToItem (uint** `nKey` **, uint** `nIndex` **);**|
|**ON_WM_HSCROLL_REFLECT ()**|**afx_msg void HScroll (uint** `nSBCode` **, uint** `nPos` **);**|
|**ON_WM_VSCROLL_REFLECT ()**|**afx_msg void VScroll (uint** `nSBCode` **, uint** `nPos` **);**|
|**ON_WM_PARENTNOTIFY_REFLECT ()**|**afx_msg void ParentNotify (uint** `message` **, lParam** `lParam` **);**|

Makra ON_NOTIFY_REFLECT i ON_CONTROL_REFLECT mają różne odmiany, które zezwalają na obsługę danego komunikatu przez więcej niż jeden obiekt (taki jak formant i jego element nadrzędny).

|Wpis mapy|Prototyp funkcji|
|---------------|------------------------|
|**ON_NOTIFY_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**AFX_MSG bool** `memberFxn` **(NMHDR** <strong>\*</strong> `pNotifyStruct` **, LRESULT** <strong>\*</strong> *wynik* **);**|
|**ON_CONTROL_REFLECT_EX (** `wNotifyCode` **,** `memberFxn` **)**|**AFX_MSG bool** `memberFxn` **( );**|

## <a name="handling-reflected-messages-an-example-of-a-reusable-control"></a>Obsługa komunikatów odbitych: przykład kontroli wielokrotnego użytku

Ten prosty przykład tworzy kontrolkę wielokrotnego użytku o nazwie `CYellowEdit` . Kontrolka działa tak samo jak w przypadku zwykłej kontrolki edycji, z tą różnicą, że w żółtym tle jest wyświetlany czarny tekst. Można łatwo dodać funkcje członkowskie, które pozwolą `CYellowEdit` formantowi wyświetlać różne kolory.

### <a name="to-try-the-example-that-creates-a-reusable-control"></a>Aby wypróbować przykład, który tworzy formant wielokrotnego użytku

1. Utwórz nowe okno dialogowe w istniejącej aplikacji. Aby uzyskać więcej informacji, zobacz temat [Edytor okien dialogowych](../windows/dialog-editor.md) .

   Musisz mieć aplikację, w której ma zostać opracowana kontrolka wielokrotnego użytku. Jeśli nie masz istniejącej aplikacji do użycia, Utwórz aplikację opartą na oknach dialogowych przy użyciu AppWizard.

2. Gdy projekt został załadowany do Visual C++, użyj ClassWizard, aby utworzyć nową klasę o nazwie `CYellowEdit` opartej na `CEdit` .

3. Dodaj trzy zmienne członkowskie do `CYellowEdit` klasy. Pierwsze dwie będą *COLORREF* zmienne, aby pomieścić kolor tekstu i kolor tła. Trzecia będzie `CBrush` obiektem, który będzie przechowywać Pędzel do rysowania tła. `CBrush`Obiekt umożliwia jednokrotne utworzenie pędzla, po prostu odwołujący się do niego, a w celu zniszczenia pędzla automatycznie, gdy `CYellowEdit` formant zostanie zniszczony.

4. Zainicjuj zmienne elementu członkowskiego, pisząc Konstruktor w następujący sposób:

    ```cpp
    CYellowEdit::CYellowEdit()
    {
        m_clrText = RGB(0, 0, 0);
        m_clrBkgnd = RGB(255, 255, 0);
        m_brBkgnd.CreateSolidBrush(m_clrBkgnd);
    }
    ```

5. Za pomocą ClassWizard Dodaj procedurę obsługi dla odbicia komunikatu WM_CTLCOLOR do `CYellowEdit` klasy. Należy zauważyć, że znak równości na początku nazwy wiadomości na liście komunikatów, który można obsłużyć, wskazuje, że komunikat jest widoczny. Jest to opisane w temacie [Definiowanie obsługi komunikatów dla wiadomości odzwierciedlonej](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).

   ClassWizard dodaje następujące makro i funkcję szkieletu mapy komunikatów:

    ```cpp
    ON_WM_CTLCOLOR_REFLECT()
    // Note: other code will be in between....

    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)
    {
        // TODO: Change any attributes of the DC here
        // TODO: Return a non-NULL brush if the
        //       parent's handler should not be called
        return NULL;
    }
    ```

6. Zastąp treść funkcji poniższym kodem. Kod określa kolor tekstu, kolor tła tekstu i kolor tła reszty formantu.

    ```cpp
    pDC->SetTextColor(m_clrText);   // text
    pDC->SetBkColor(m_clrBkgnd);    // text bkgnd
    return m_brBkgnd;               // ctl bkgnd
    ```

7. Utwórz kontrolkę Edycja w oknie dialogowym, a następnie Dołącz ją do zmiennej składowej przez dwukrotne kliknięcie kontrolki edycji, przytrzymując klawisz Control. W oknie dialogowym Dodaj zmienną członkowską Wypełnij pole Nazwa zmiennej i wybierz "formant" dla kategorii, a następnie "CYellowEdit" dla typu zmiennej. Nie zapomnij ustawić kolejności tabulacji w oknie dialogowym. Upewnij się również, że `CYellowEdit` w pliku nagłówkowym okna dialogowego znajduje się plik nagłówka kontrolki.

8. Kompiluj i uruchamiaj aplikację. Kontrolka edycji będzie miała żółte tło.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
