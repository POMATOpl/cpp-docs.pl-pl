---
description: 'Dowiedz się więcej na temat: funkcje interfejsu użytkownika, Kreator aplikacji MFC'
title: Funkcje interfejsu użytkownika, kreator aplikacji MFC
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.ui
helpviewer_keywords:
- MFC Application Wizard, user interface features
ms.assetid: 59e7b829-a665-42eb-be23-3f2a36eb2dad
ms.openlocfilehash: ac2c3dc7881fd5e931539224bed121c617b940a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218514"
---
# <a name="user-interface-features-mfc-application-wizard"></a>Funkcje interfejsu użytkownika, kreator aplikacji MFC

W tym temacie opisano opcje, których można użyć do określenia wyglądu aplikacji. Funkcje interfejsu użytkownika dostępne dla projektu zależą od typu aplikacji określonej w Kreatorze aplikacji MFC na stronie [Typ aplikacji](../../mfc/reference/application-type-mfc-application-wizard.md) . Jeśli na przykład utworzysz aplikację jednostronicowego interfejsu dokumentu, nie można dodać stylów ramki podrzędnej.

- **Style ramki głównej**

   Ustawia funkcje ramki głównego okna aplikacji.

   |Opcja|Opis|
   |------------|-----------------|
   |**Gruba ramka**|Tworzy okno, które ma obramowanie o wymiarze. Domyślnie.|
   |**Pole minimalizowania**|Zawiera pole Minimalizuj w oknie głównym ramki. Domyślnie.|
   |**Maksymalizuj pole**|Zawiera pole Maksymalizuj w głównym oknie ramki. Domyślnie.|
   |**Zminimalizowane**|Otwiera okno głównej ramki jako ikonę.|
   |**Zmaksymalizowane**|Otwiera okno głównej ramki do pełnego rozmiaru ekranu.|
   |**Menu systemowe**|Zawiera menu systemowe w oknie głównym ramki. Domyślnie.|
   |**Informacje o usłudze Box**|Zawiera pole **Informacje o** aplikacji. Użytkownik może uzyskać dostęp do tego pola z menu **Pomoc** aplikacji. Domyślny i niezmieniony, chyba że wybierzesz pozycję **okno dialogowe**, na stronie [Kreator aplikacji MFC](../../mfc/reference/application-type-mfc-application-wizard.md) .<br /><br /> **Uwaga** Zazwyczaj niedostępna opcja oznacza, że Kreator nie stosuje opcji do projektu, bez względu na to, czy pole wyboru niedostępnego elementu jest zaznaczone lub wyczyszczone. W takim przypadku Kreator zawsze dodaje okno **informacje** do projektu, chyba że najpierw określisz projekt jako okno dialogowe, a następnie usuń zaznaczenie tego pola.|
   |**Początkowy pasek stanu**|Dodaje pasek stanu do aplikacji. Pasek stanu zawiera automatyczne wskaźniki dla Caps Lock klawiatury, NUM LOCK i SCROLL LOCK Keys oraz wiersz komunikatu, który wyświetla ciągi pomocy dla poleceń menu i przycisków paska narzędzi. Kliknięcie tej opcji powoduje również dodanie poleceń menu do wyświetlania lub ukrywania paska stanu. Domyślnie aplikacja ma pasek stanu. Niedostępne dla typów aplikacji opartych na oknach dialogowych.|
   |**Podziel okno**|Udostępnia pasek rozdzielacza. Pasek rozdzielacza dzieli główne widoki aplikacji. W aplikacji interfejsu wielu dokumentów (MDI) okno klienta ramki podrzędnej MDI jest oknem rozdzielacza, a w aplikacji interfejs pojedynczego dokumentu (SDI) i aplikacji z wieloma dokumentami najwyższego poziomu okno klienta ramki głównej jest oknem rozdzielacza. Niedostępne dla typów aplikacji opartych na oknach dialogowych.|

- **Style ramki podrzędnej**

   Określa wygląd i początkowy stan ramek podrzędnych w aplikacji. Style ramki podrzędnej są dostępne tylko dla aplikacji MDI.

   |Opcja|Opis|
   |------------|-----------------|
   |**Pole minimalizowania elementu podrzędnego**|Określa, czy okno podrzędne ma przycisk Minimalizuj (domyślnie włączone).|
   |**Pole maksymalizowania elementu podrzędnego**|Określa, czy okno podrzędne ma przycisk Maksymalizuj (domyślnie włączone).|
   |**Element podrzędny zmaksymalizowany**|Określa, czy okno podrzędne jest początkowo maksymalizowane przez ustawienie flagi cs. Style WS_MAXIMIZE w funkcji składowej [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow) `CChildFrame` .|

- **Paski poleceń (menu/pasek narzędzi/wstążka)**

   Wskazuje, czy aplikacja zawiera menu, paski narzędzi i/lub Wstążkę. Niedostępne w przypadku aplikacji opartych na oknach dialogowych.

   |Opcja|Opis|
   |------------|-----------------|
   |**Korzystanie z klasycznego menu**|Określa, że aplikacja zawiera klasyczne menu, którego nie można przeciągać.|
   |**Korzystanie z klasycznego zadokowanego paska narzędzi**|Dodaje standardowy pasek narzędzi systemu Windows do aplikacji. Pasek narzędzi zawiera przyciski do tworzenia nowego dokumentu. otwieranie i zapisywanie plików dokumentów; Wycinanie kopiowania, wklejania lub drukowania tekstu; i przechodzenie do trybu pomocy. Włączenie tej opcji powoduje również dodanie poleceń menu do wyświetlania lub ukrywania paska narzędzi.|
   |**Użyj paska narzędzi stylu przeglądarki**|Dodaje do aplikacji pasek narzędzi w stylu programu Internet Explorer.|
   |**Użyj paska menu i paska narzędzi**|Wskazuje, że aplikacja zawiera pasek menu do przeciągnięciu i pasek narzędzi.|
   |**Paski narzędzi i obrazy zdefiniowane przez użytkownika**|Zezwala użytkownikowi na Dostosowywanie paska narzędzi i obrazów pasków narzędzi w środowisku uruchomieniowym.|
   |**Spersonalizowane zachowanie menu**|Określa, czy menu zawiera pełną listę elementów, gdy jest otwarta, lub jeśli zawiera tylko te polecenia, które użytkownik najczęściej używa.|
   |**Korzystanie ze wstążki**|Używa wstążki podobnej do 2007 w aplikacji zamiast paska menu lub paska narzędzi.|

- **Tytuł okna dialogowego**

   W przypadku aplikacji opartych na [klasie CDialog](../../mfc/reference/cdialog-class.md)ten tytuł pojawia się na pasku tytułu okna dialogowego. Aby edytować to pole, należy najpierw wybrać opcję **opartą na oknach dialogowych** w obszarze **Typ aplikacji**. Aby uzyskać więcej informacji, zobacz [Typ aplikacji, Kreator aplikacji MFC](../../mfc/reference/application-type-mfc-application-wizard.md).

## <a name="see-also"></a>Zobacz też

[Kreator aplikacji MFC](../../mfc/reference/mfc-application-wizard.md)
