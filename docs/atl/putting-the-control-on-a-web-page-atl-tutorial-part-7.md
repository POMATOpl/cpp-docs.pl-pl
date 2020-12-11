---
description: 'Dowiedz się więcej na temat: umieszczanie kontrolki na stronie sieci Web (samouczek ATL, część 7)'
title: Umieszczanie kontrolki na stronie sieci Web (ALT — Samouczek, część 7)
ms.custom: get-started-article
ms.date: 05/06/2019
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
ms.openlocfilehash: 738d847a6436a2afab2e336502ec3255d1a1e589
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159182"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>Umieszczanie kontrolki na stronie sieci Web (ALT — Samouczek, część 7)

Kontrolka została zakończona. Aby sprawdzić, czy kontrolka pracuje w świecie rzeczywistym, umieść ją na stronie sieci Web. Plik HTML, który zawiera kontrolkę, został utworzony podczas definiowania formantu. Otwórz plik PolyCtl.htm z **Eksplorator rozwiązań** i możesz zobaczyć swój formant na stronie sieci Web.

W tym kroku dodasz funkcję do kontrolki i skryptuje stronę sieci Web w celu reagowania na zdarzenia. Zmodyfikujesz również formant, aby umożliwić programowi Internet Explorer znajomość kontroli nad wykonywaniem skryptów.

## <a name="adding-new-functionality"></a>Dodawanie nowych funkcji

### <a name="to-add-control-features"></a>Aby dodać funkcje kontroli

1. Otwórz PolyCtl. cpp i Zastąp następujący kod:

    ```cpp
    if (PtInRegion(hRgn, xPos, yPos))
        Fire_ClickIn(xPos, yPos);
    else
        Fire_ClickOut(xPos, yPos);
    ```

    with

    ```cpp
    short temp = m_nSides;
    if (PtInRegion(hRgn, xPos, yPos))
    {
        Fire_ClickIn(xPos, yPos);
        put_Sides(++temp);
    }
    else
    {
        Fire_ClickOut(xPos, yPos);
        put_Sides(--temp);
    }
    ```

Kształt będzie teraz dodawać i usuwać boki w zależności od tego, gdzie klikniesz.

## <a name="scripting-the-web-page"></a>Wykonywanie skryptów na stronie sieci Web

Kontrolka nie wykonuje jeszcze żadnych czynności, więc Zmień stronę sieci Web tak, aby odpowiadała na wysyłane zdarzenia.

### <a name="to-script-the-web-page"></a>Aby zaskryptować stronę sieci Web

1. Otwórz PolyCtl.htm i wybierz pozycję widok HTML. Dodaj następujące wiersze do kodu HTML. Należy je dodać po tej dacie `</OBJECT>` `</BODY>` .

    ```html
    <SCRIPT LANGUAGE="VBScript">
    <!--
        Sub PolyCtl_ClickIn(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - adding side")
        End Sub
        Sub PolyCtl_ClickOut(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - removing side")
        End Sub
    -->
    </SCRIPT>
    ```

1. Zapisz plik HTM.

Dodano jakiś kod VBScript, który pobiera właściwość boki z formantu. Zwiększa liczbę stron po kliknięciu wewnątrz kontrolki. Kliknięcie poza kontrolką zmniejsza liczbę boków.

## <a name="indicating-that-the-control-is-safe-for-scripting"></a>Wskazuje, że formant jest bezpieczny dla skryptów

Możesz wyświetlić stronę sieci Web z kontrolką tylko w programie Internet Explorer. Inne przeglądarki nie obsługują już formantów ActiveX ze względu na słabe zabezpieczenia.

> [!NOTE]
> Jeśli formant nie jest widoczny, należy pamiętać, że niektóre przeglądarki wymagają dopasowania ustawień do uruchamiania formantów ActiveX. Zapoznaj się z dokumentacją przeglądarki, aby włączyć kontrolki ActiveX.

W oparciu o bieżące ustawienia zabezpieczeń programu Internet Explorer może pojawić się okno dialogowe Alert zabezpieczeń. Stwierdza, że formant może nie być bezpieczny dla skryptu i może być uszkodzony. Na przykład jeśli masz kontrolkę, która wyświetla plik, ale miała także `Delete` metodę, która usunęła plik, będzie ona bezpieczna, jeśli zostanie ona przejrzana na stronie. Nie byłoby to jednak bezpieczne dla skryptu, ponieważ ktoś mógłby wywołać `Delete` metodę.

> [!IMPORTANT]
> W tym samouczku można zmienić ustawienia zabezpieczeń w programie Internet Explorer, aby uruchamiać kontrolki ActiveX, które nie są oznaczone jako bezpieczne. W panelu sterowania kliknij pozycję **Właściwości internetowe** , a następnie kliknij pozycję **zabezpieczenia** , aby zmienić odpowiednie ustawienia. Po ukończeniu tego samouczka Zmień ustawienia zabezpieczeń z powrotem na pierwotny stan.

Można programowo ostrzec program Internet Explorer, że nie musi on wyświetlać okna dialogowego Alert zabezpieczeń dla tej konkretnej kontrolki. Można to zrobić za pomocą `IObjectSafety` interfejsu. ATL udostępnia implementację tego interfejsu w klasie [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md). Aby dodać interfejs do kontrolki, Dodaj `IObjectSafetyImpl` do listy dziedziczonych klas i Dodaj do niej wpis na mapie com.

### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>Aby dodać IObjectSafetyImpl do kontrolki

1. Dodaj następujący wiersz na końcu listy dziedziczonych klas w PolyCtl. h i Dodaj przecinek do poprzedniego wiersza:

    [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]

1. Dodaj następujący wiersz do mapy COM w PolyCtl. h:

    [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]

## <a name="building-and-testing-the-control"></a>Kompilowanie i testowanie kontrolki

Kompiluj formant. Po zakończeniu kompilacji Otwórz ponownie PolyCtl.htm w widoku przeglądarki. Tym razem strona sieci Web powinna być wyświetlana bezpośrednio bez okna dialogowego **alert o zabezpieczeniach** . Jeśli klikniesz wewnątrz wielokąta, liczba boków rośnie o jeden. Kliknij poza wielokątem, aby zmniejszyć liczbę boków.

[Wróć do kroku 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="next-steps"></a>Następne kroki

Ten krok zawiera samouczek ATL. Aby uzyskać linki do dodatkowych informacji na temat biblioteki ATL, zobacz [stronę startową ATL](../atl/active-template-library-atl-concepts.md).

## <a name="see-also"></a>Zobacz też

[Samouczek](../atl/active-template-library-atl-tutorial.md)
