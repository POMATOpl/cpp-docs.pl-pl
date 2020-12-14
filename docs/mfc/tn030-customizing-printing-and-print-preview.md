---
description: 'Dowiedz się więcej na temat: TN030: dostosowywanie drukowania i podglądu wydruku'
title: 'TN030: dostosowywanie drukowania i podglądu wydruku'
ms.date: 06/28/2018
f1_keywords:
- vc.print
helpviewer_keywords:
- TN030
- customizing printing and print preview
- printing [MFC], views
- printing views [MFC]
- print preview [MFC], customizing
ms.assetid: 32744697-c91c-41b6-9a12-b8ec01e0d438
ms.openlocfilehash: 6fc0571b908f85b24b8a0752a00842077d537dce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215615"
---
# <a name="tn030-customizing-printing-and-print-preview"></a>TN030: dostosowywanie drukowania i podglądu wydruku

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga zawiera opis procesu dostosowywania drukowania i podglądu wydruku oraz opis celów procedur wywołania zwrotnego używanych w programie `CView` oraz procedurach wywołania zwrotnego i funkcji składowych `CPreviewView` .

## <a name="the-problem"></a>Problem

MFC oferuje kompletne rozwiązanie dla większości potrzeb drukowania i podglądu wydruku. W większości przypadków niezbędny jest niewielki dodatkowy kod, który może być w stanie wydrukować i wyświetlić podgląd. Istnieją jednak sposoby na optymalizację drukowania, które wymagają znaczącego wysiłku związanego z częścią dewelopera, a niektóre aplikacje muszą dodać elementy interfejsu użytkownika do trybu podglądu wydruku.

## <a name="efficient-printing"></a>Wydajne drukowanie

Gdy aplikacja MFC drukuje przy użyciu standardowych metod, system Windows kieruje wszystkie wywołania wyjściowe interfejsu urządzenia graficznego (GDI) do metapliku w pamięci. Gdy `EndPage` jest wywoływana, system Windows odtwarza metaplik jednokrotnie dla każdego fizycznego pasma wymaganego przez drukarkę do drukowania jednej strony. Podczas tego renderowania interfejs GDI często bada procedurę Abort, aby określić, czy ma ona być kontynuowana. Zazwyczaj procedura Abort umożliwia przetwarzanie komunikatów, aby użytkownik mógł przerwać zadanie drukowania przy użyciu okna dialogowego drukowania.

Niestety, może to spowolnić proces drukowania. Jeśli drukowanie w aplikacji musi być szybsze niż można osiągnąć przy użyciu standardowej techniki, należy zaimplementować ręczne przedziały.

## <a name="print-banding"></a>Paski drukowania

Aby ręcznie przedziałować, należy ponownie zaimplementować pętlę drukowania taką, która `OnPrint` jest wywoływana wiele razy na stronę (raz na pasmo). Pętla drukowania jest zaimplementowana w `OnFilePrint` funkcji w viewprnt. cpp. W `CView` klasie pochodnej należy przeciążyć tę funkcję, aby wpis mapy komunikatów do obsługi polecenia Print wywołuje funkcję Print. Skopiuj `OnFilePrint` procedurę i Zmień pętlę drukowania, aby zaimplementować przedziały. Prawdopodobnie chcesz również przekazać prostokąt przedziału do funkcji drukowania, aby można było zoptymalizować rysowanie na podstawie sekcji drukowanej strony.

Po drugie, należy często wywołać `QueryAbort` podczas rysowania pasma. W przeciwnym razie procedura Abort nie zostanie wywołana i użytkownik nie będzie mógł anulować zadania drukowania.

## <a name="print-preview-electronic-paper-with-user-interface"></a>Podgląd wydruku: papier elektroniczny z interfejsem użytkownika

Podgląd wydruku, w zasadzie, próbuje włączyć ekran do emulacji drukarki. Domyślnie obszar klienta okna głównego jest używany do wyświetlania jednej lub dwóch stron w pełni w oknie. Użytkownik może powiększyć w obszarze strony, aby zobaczyć go bardziej szczegółowo. W celu uzyskania dodatkowej pomocy użytkownik może nawet być uprawniony do edytowania dokumentu w trybie podglądu.

## <a name="customizing-print-preview"></a>Dostosowywanie podglądu wydruku

Ta uwaga dotyczy tylko jednego aspektu modyfikowania podglądu wydruku: Dodawanie interfejsu użytkownika do trybu podglądu. Możliwe są inne modyfikacje, ale te zmiany znajdują się poza zakresem tej dyskusji.

## <a name="to-add-ui-to-the-preview-mode"></a>Aby dodać interfejs użytkownika do trybu podglądu

1. Utwórz klasę widoku od `CPreviewView` .

2. Dodaj programy obsługi poleceń dla żądanych aspektów interfejsu użytkownika.

3. Jeśli dodajesz aspekty wizualne do ekranu, Przesłoń `OnDraw` i przeprowadź rysowanie po wywołaniu `CPreviewView::OnDraw` .

## <a name="onfileprintpreview"></a>OnFilePrintPreview

Jest to procedura obsługi poleceń dla podglądu wydruku. Jego domyślna implementacja to:

```cpp
void CView::OnFilePrintPreview()
{
    // In derived classes, implement special window handling here
    // Be sure to Unhook Frame Window close if hooked.

    // must not create this on the frame. Must outlive this function
    CPrintPreviewState* pState = new CPrintPreviewState;

    if (!DoPrintPreview(AFX_IDD_PREVIEW_TOOLBAR, this,
        RUNTIME_CLASS(CPreviewView), pState))
    {
        // In derived classes, reverse special window handling
        // here for Preview failure case

        TRACE0("Error: DoPrintPreview failed");
        AfxMessageBox(AFX_IDP_COMMAND_FAILURE);
        delete pState;  // preview failed to initialize, delete State now
    }
}
```

`DoPrintPreview` spowoduje ukrycie głównego okienka aplikacji. Paski sterowania, takie jak pasek stanu, można zachować, określając je w składowej pState->*dwStates* (jest to maska bitów, a bity poszczególnych pasków sterowania są zdefiniowane przez AFX_CONTROLBAR_MASK (AFX_IDW_MYBAR)). Okno pState->*nIDMainPane* to okno, które będzie automatycznie ukrywane i wyświetlane. `DoPrintPreview` następnie utworzy pasek przycisków dla standardowego interfejsu użytkownika w wersji zapoznawczej. Jeśli jest wymagana obsługa okien specjalnych, na przykład aby ukryć lub pokazać inne okna, które należy wykonać przed `DoPrintPreview` wywołaniem.

Domyślnie po zakończeniu podglądu wydruku funkcja zwraca paski kontroli do ich oryginalnych stanów i okienka głównego. Jeśli wymagana jest obsługa specjalna, należy wykonać przesłonięcie `EndPrintPreview` . Jeśli to `DoPrintPreview` się nie powiedzie, Zapewnij również obsługę specjalną.

DoPrintPreview jest wywoływana z:

- Identyfikator zasobu szablonu okna dialogowego dla paska narzędzi podglądu.

- Wskaźnik do widoku w celu przeprowadzenia drukowania w podglądzie wydruku.

- Klasa czasu wykonywania klasy widoku podglądu. Ta zostanie utworzona dynamicznie w DoPrintPreview.

- Wskaźnik CPrintPreviewState. Należy pamiętać, że struktura CPrintPreviewState (lub struktura pochodna, jeśli aplikacja wymaga więcej informacji o stanie zachowane) *nie* może być utworzona w ramce. DoPrintPreview jest niemodalny, a struktura musi przetrwać do momentu wywołania EndPrintPreview.

  > [!NOTE]
  > Jeśli do obsługi drukowania jest wymagana oddzielna Klasa widoku lub widoku, wskaźnik do tego obiektu powinien zostać przesłany jako drugi parametr.

## <a name="endprintpreview"></a>EndPrintPreview

Jest to wywoływane, aby zakończyć tryb podglądu wydruku. Często pożądane jest przechodzenie do strony w dokumencie, który był ostatnio wyświetlany w podglądzie wydruku. `EndPrintPreview` to szansa aplikacji. Element członkowski pInfo >*m_nCurPage* jest stroną, która była ostatnio wyświetlana (po lewej stronie, gdy Wyświetlono dwie strony), a wskaźnik jest wskazówką dotyczącą miejsca, w którym użytkownik zainteresuje. Ze względu na to, że struktura widoku aplikacji jest nieznana dla struktury, należy podać kod do przejścia do wybranego punktu.

Przed wywołaniem należy wykonać większość akcji `CView::EndPrintPreview` . To wywołanie odwraca skutki działania `DoPrintPreview` i usuwa pView, PDC oraz pInfo.

```cpp
// Any further cleanup should be done here.
CView::EndPrintPreview(pDC, pInfo, point, pView);
```

## <a name="cwinapponfileprintsetup"></a>CWinApp:: OnFilePrintSetup

Ta wartość musi być zamapowana dla elementu menu konfiguracji drukowania. W większości przypadków nie jest konieczne przesłonięcie implementacji.

## <a name="page-nomenclature"></a>Nomenklatura strony

Innym problemem jest numerowanie stron i ich kolejność. W przypadku prostych aplikacji typu edytor tekstów jest to problem bardzo prosty. Większość systemów podglądu wydruku zakłada, że każda wydrukowana strona odpowiada jednej stronie dokumentu.

W przypadku próby udostępnienia uogólnionego rozwiązania należy rozważyć kilka rzeczy. Wyobraź sobie system CAD. Użytkownik ma rysunek, który obejmuje kilka arkuszy elektronicznych. W przypadku plotera o rozmiarze elektronicznym (lub mniejszym, skalowanym) numeracja stron będzie jak w prostym przypadku. Jednak na drukarce laserowej drukuje 16 stron o rozmiarze na jednym arkuszu, co w podglądzie wydruku uwzględnia "stronę"

Zgodnie z postanowieniami akapitu wprowadzającego Podgląd wydruku działa jak drukarka. W związku z tym użytkownik zobaczy, co się stało z konkretną wybraną drukarką. Jest to widok, aby określić, który obraz jest drukowany na każdej stronie.

Ciąg opisu strony w `CPrintInfo` strukturze zawiera sposób wyświetlania numeru strony użytkownikowi, jeśli może być reprezentowany jako jedna liczba na stronę (jak w "Strona 1" lub "strony 1-2"). Ten ciąg jest używany przez domyślną implementację programu `CPreviewView::OnDisplayPageNumber` . Jeśli jest wymagana inna wartość ekranu, może ona zastąpić tę funkcję wirtualną, na przykład "Arkusz1, sekcje A, B".

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
