---
description: 'Dowiedz się więcej o: funkcjach członkowskich kontrolki suwaka'
title: Funkcje członkowskie formantu suwaka
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
ms.openlocfilehash: 57108872a779bc4876be89afd5b81008f69a0837
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216902"
---
# <a name="slider-control-member-functions"></a>Funkcje członkowskie formantu suwaka

Aplikacja może wywoływać funkcje składowe kontrolki suwaka, aby pobrać informacje o kontrolce suwaka ([Korzystanie CSliderCtrl](../mfc/reference/csliderctrl-class.md)) i zmienić jej cechy.

Aby pobrać pozycję suwaka (czyli wartość wybraną przez użytkownika), użyj funkcji składowej [GetPos](../mfc/reference/csliderctrl-class.md#getpos) . Aby ustawić położenie suwaka, użyj funkcji składowej [SetPos](../mfc/reference/csliderctrl-class.md#setpos) . W dowolnym momencie można użyć `VerifyPos` funkcji elementu członkowskiego, aby upewnić się, że suwak znajduje się pomiędzy wartością minimalną i maksymalną.

Zakres kontrolki suwaka to zbiór wartości ciągłych, które może reprezentować formant Slider. Większość aplikacji używa funkcji składowej [SetRange](../mfc/reference/csliderctrl-class.md#setrange) w celu ustawienia zakresu kontrolki suwaka podczas jej pierwszego utworzenia. Aplikacje mogą dynamicznie zmieniać zakres po utworzeniu kontrolki suwaka przy użyciu funkcji składowych [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) i [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) . Aplikacja, która pozwala na zmianę zakresu dynamicznie, zazwyczaj pobiera ustawienia zakresu końcowego, gdy użytkownik zakończy pracę z kontrolką suwaka. Aby pobrać te ustawienia, należy użyć funkcji elementów członkowskich [GetRange](../mfc/reference/csliderctrl-class.md#getrange), [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax)i [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) .

Aplikacja może używać stylu TBS_AUTOTICKS, aby wyświetlić znaczniki kontrolki znacznika suwaka automatycznie. Jeśli aplikacja wymaga kontroli pozycji lub częstotliwości znaczników, można użyć wielu funkcji składowych.

Aby ustawić położenie znacznika, aplikacja może używać funkcji składowej [SetTic](../mfc/reference/csliderctrl-class.md#settic) . Funkcja członkowska [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq) umożliwia aplikacji Ustawianie znaczników, które pojawiają się w regularnych odstępach czasu formantu suwaka. Na przykład aplikacja może używać tej funkcji elementu członkowskiego do wyświetlania tylko 10 znaczników w zakresie od 1 do 100.

Aby pobrać indeks z zakresu odpowiadającego znacznikowi znacznika, użyj funkcji składowej [GetTic](../mfc/reference/csliderctrl-class.md#gettic) . Funkcja członkowska [GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray) pobiera tablicę tych indeksów. Aby pobrać pozycję znacznika, we współrzędnych klienta Użyj funkcji składowej [GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos) . Aplikacja może pobrać liczbę znaczników przy użyciu funkcji składowej [GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics) .

Funkcja członkowska [ClearTics](../mfc/reference/csliderctrl-class.md#cleartics) usuwa wszystkie znaczniki kontrolki suwaka.

Rozmiar linii kontrolki suwaka określa, jak daleko suwak jest przenoszony, gdy aplikacja otrzymuje TB_LINEDOWN lub TB_LINEUP komunikat powiadomienia. Podobnie rozmiar strony określa odpowiedź do TB_PAGEDOWN i TB_PAGEUP komunikatów powiadomień. Aplikacje mogą pobierać i ustawiać wartości rozmiaru wiersza i strony przy użyciu funkcji składowych [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize), [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize), [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize)i [SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize) .

Aplikacja może używać funkcji elementów członkowskich do pobierania wymiarów kontrolki suwaka. Funkcja członkowska [GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect) pobiera prostokąt ograniczenia dla suwaka. Funkcja członkowska [GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect) pobiera prostokąt obwiedni dla kanału kontrolki suwak. (Kanał to obszar, nad którym suwak jest przenoszony i który zawiera wyróżnianie, gdy wybrany jest zakres.)

Jeśli kontrolka suwaka ma styl TBS_ENABLESELRANGE, użytkownik może wybrać zakres ciągłego wartości. Wiele funkcji składowych pozwala na dynamiczne dopasowanie zakresu wyboru. Funkcja elementu członkowskiego [setselect](../mfc/reference/csliderctrl-class.md#setselection) ustawia początkową i końcową pozycję zaznaczenia. Gdy użytkownik zakończył Ustawianie zakresu wyboru, aplikacja może pobrać ustawienia za pomocą funkcji składowej [getselect](../mfc/reference/csliderctrl-class.md#getselection) . Aby wyczyścić wybór użytkownika, użyj funkcji składowej [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel) .

## <a name="see-also"></a>Zobacz też

[Korzystanie z CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
