---
description: 'Dowiedz się więcej na temat: TN021: routing poleceń i komunikatów'
title: 'TN021: routing poleceń i komunikatów'
ms.date: 06/28/2018
f1_keywords:
- vc.routing
helpviewer_keywords:
- TN021
- command routing [MFC], technical note TN021
- Windows messages [MFC], routing
ms.assetid: b5952c8b-123e-406c-a36d-a6ac7c6df307
ms.openlocfilehash: 3cc481585fa2f1eacc3deb575e163d5a1644002c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215849"
---
# <a name="tn021-command-and-message-routing"></a>TN021: routing poleceń i komunikatów

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

W tej uwadze opisano Routing i architekturę wysyłania poleceń oraz zaawansowane tematy w obszarze Ogólne Routing komunikatów okna.

Zapoznaj się z Visual C++, aby uzyskać ogólne informacje dotyczące architektur opisanych w tym miejscu, szczególnie różnice między komunikatami systemu Windows, powiadomieniami kontroli i poleceniami. W tej uwadze założono, że wiesz już, jak rozwiązywać problemy opisane w wydrukowanej dokumentacji i dotyczy tylko bardzo zaawansowanych tematów.

## <a name="command-routing-and-dispatch-mfc-10-functionality-evolves-to-mfc-20-architecture"></a>Funkcja routingu i wysyłania poleceń MFC 1,0 jest zmieniana na architekturę MFC 2,0

System Windows ma WM_COMMAND komunikat, który jest przeciążony do dostarczania powiadomień o poleceniach menu, klawiszy skrótów i powiadomieniach o kontrolkach okna dialogowego.

MFC 1,0 zostało utworzone na nieco przez umożliwienie procedury obsługi polecenia (na przykład "OnFileNew") w `CWnd` klasie pochodnej do wywołania w odpowiedzi na konkretne WM_COMMAND. Jest to przyklejane wraz ze strukturą danych o nazwie Mapa wiadomości i powoduje, że jest to bardzo wydajny mechanizm poleceń.

MFC 1,0 udostępnia także dodatkowe funkcje oddzielające powiadomienia sterujące z komunikatów poleceń. Polecenia są reprezentowane przez 16-bitowy identyfikator, czasami znany jako identyfikator polecenia. Polecenia zwykle zaczynają się od `CFrameWnd` (czyli menu wybierają lub tłumaczy Akcelerator) i są kierowane do różnych innych okien.

MFC 1,0 użycie polecenia routingu w ograniczonym sensie dla implementacji interfejsu wielu dokumentów (MDI). (W oknie ramka MDI polecenia są delegowane do aktywnego okna podrzędnego MDI).

Ta funkcja została uogólniona i rozszerzona w bibliotece MFC 2,0, aby umożliwić obsługę poleceń przez szerszy zakres obiektów (nie tylko obiektów okien). Zapewnia bardziej formalną i rozszerzalną architekturę do routingu komunikatów i ponownie używa routingu docelowego polecenia dla nie tylko obsługi poleceń, ale również do aktualizowania obiektów interfejsu użytkownika (takich jak elementy menu i przyciski paska narzędzi), aby odzwierciedlić bieżącą dostępność polecenia.

## <a name="command-ids"></a>Identyfikatory poleceń

Aby uzyskać wyjaśnienie procesu routingu i powiązania poleceń, zobacz Visual C++. [Uwaga techniczna 20](../mfc/tn020-id-naming-and-numbering-conventions.md) zawiera informacje na temat nazewnictwa identyfikatorów.

Do identyfikatorów poleceń używamy prefiksu ogólnego "ID_". Identyfikatory poleceń są >= 0x8000. W wierszu komunikatu lub pasku stanu będzie wyświetlany ciąg opisu polecenia, jeśli istnieje zasób typu STRING z tymi samymi identyfikatorami, które są identyfikatora polecenia.

W zasobach aplikacji identyfikator polecenia może pojawić się w kilku miejscach:

- W jednym z zasobów CIĄGÓW, który ma taki sam identyfikator jak monit wiersza wiadomości.

- W prawdopodobnie wielu zasobach MENU, które są dołączone do elementów menu, które wywołują to samo polecenie.

- (Zaawansowane) w przycisku okna dialogowego dla polecenia GOSUB.

W kodzie źródłowym aplikacji identyfikator polecenia może pojawić się w kilku miejscach:

- W zasobie. H (lub inny główny plik nagłówka symboli) do definiowania identyfikatorów poleceń specyficznych dla aplikacji.

- BYĆ może w tablicy identyfikatorów używanej do tworzenia paska narzędzi.

- W ON_COMMAND makro.

- BYĆ może w ON_UPDATE_COMMAND_UI makro.

Obecnie jedyną implementacją w MFC wymagającą identyfikatorów poleceń jest >= 0x8000 jest implementacją okien dialogowych/poleceń GOSUB.

## <a name="gosub-commands-using-command-architecture-in-dialogs"></a>Polecenia GOSUB, używanie architektury poleceń w oknach dialogowych

Architektura poleceń routingu i włączania poleceń działa dobrze w przypadku okien ramowych, elementów menu, przycisków paska narzędzi, przycisków paska dialogowego, innych pasków sterowania i innych elementów interfejsu użytkownika przeznaczonych do aktualizacji poleceń na żądanie i trasy oraz do sterowania identyfikatorami do głównego obiektu docelowego polecenia (zazwyczaj okno ramki głównej). Ten obiekt docelowy polecenia głównego może skierować polecenie lub powiadomienia kontroli do innych obiektów docelowych poleceń stosownie do potrzeb.

Okno dialogowe (modalne lub niemodalne) może korzystać z niektórych funkcji architektury poleceń, Jeśli przypiszesz identyfikator kontrolki okna dialogowego do odpowiedniego identyfikatora polecenia. Obsługa okien dialogowych nie jest automatyczna, dlatego może być konieczne napisanie dodatkowego kodu.

Należy pamiętać, że aby wszystkie te funkcje działały prawidłowo, identyfikatory poleceń powinny być >= 0x8000. Ze względu na to, że wiele okien dialogowych może być kierowanych do tej samej ramki, udostępnione polecenia powinny być >= 0x8000, a nieudostępnione IDCs w określonym oknie dialogowym powinny być <= 0x7FFF.

Możesz umieścić normalny przycisk w normalnym modalnym oknie dialogowym z IDC zestawu przycisków ustawionym na odpowiedni identyfikator polecenia. Gdy użytkownik wybierze przycisk, właściciel okna dialogowego (zwykle okno głównej ramki) pobiera polecenie podobnie jak każde inne polecenie. Jest to nazywane GOSUB poleceniem, ponieważ jest zwykle używane do wyłączenia kolejnego okna dialogowego (GOSUB pierwszego okna dialogowego).

Możesz również wywołać funkcję `CWnd::UpdateDialogControls` w oknie dialogowym i przekazać ją do adresu głównego okna ramki. Ta funkcja włącza lub wyłącza kontrolki okna dialogowego w zależności od tego, czy zawierają one programy obsługi poleceń w ramce. Ta funkcja jest wywoływana automatycznie w przypadku pasków sterowania w pętli bezczynności aplikacji, ale należy wywołać ją bezpośrednio dla zwykłych okien dialogowych, które mają mieć tę funkcję.

## <a name="when-on_update_command_ui-is-called"></a>Gdy ON_UPDATE_COMMAND_UI jest wywoływana

Utrzymywanie stanu włączenia/zaznaczenia wszystkich elementów menu programu przez cały czas może być niedrogim kosztownym problemem. Typową techniką jest włączenie/sprawdzenie elementów menu tylko wtedy, gdy użytkownik wybierze menu podręczne. Implementacja MFC 2,0 `CFrameWnd` obsługuje komunikat WM_INITMENUPOPUP i używa architektury routingu poleceń do określenia stanu menu za pośrednictwem programów obsługi ON_UPDATE_COMMAND_UI.

`CFrameWnd` obsługuje również komunikat WM_ENTERIDLE, aby opisać bieżący element menu wybrany na pasku stanu (znany również jako wiersz wiadomości).

Struktura menu aplikacji edytowana przez Visual C++ jest używana do reprezentowania potencjalnych poleceń dostępnych w czasie WM_INITMENUPOPUP. Programy obsługi ON_UPDATE_COMMAND_UI mogą modyfikować stan lub tekst menu lub w przypadku zaawansowanych zastosowanych (takich jak lista MRU plików lub menu podręczne zleceń OLE), a w rzeczywistości modyfikować strukturę menu przed narysowaniem menu.

Ta sama kolejność przetwarzania ON_UPDATE_COMMAND_UI jest wykonywana dla pasków narzędzi (i innych pasków sterowania), gdy aplikacja przejdzie do jej pętli bezczynności. Aby uzyskać więcej informacji na temat pasków sterowania, zobacz *Dokumentacja biblioteki klas* i [Uwaga techniczna 31](../mfc/tn031-control-bars.md) .

## <a name="nested-pop-up-menus"></a>Zagnieżdżone menu wyskakujące

Jeśli używasz zagnieżdżonej struktury menu, Zauważ, że program obsługi ON_UPDATE_COMMAND_UI dla pierwszego elementu menu w menu podręcznym jest wywoływany w dwóch różnych przypadkach.

Po pierwsze jest wywoływana dla samego menu podręcznego. Jest to konieczne, ponieważ menu podręczne nie mają identyfikatorów i używamy identyfikatora pierwszego elementu menu menu podręcznego, aby odwołać się do całego menu podręcznego. W takim przypadku *m_pSubMenu* zmienna członkowska `CCmdUI` obiektu będzie mieć wartość różną od null i będzie wskazywała menu podręczne.

Po drugie, jest wywoływana tuż przed narysowaniem elementów menu w menu podręcznym. W tym przypadku identyfikator odwołuje się tylko do pierwszego elementu menu, a zmienna członkowska *m_pSubMenu* `CCmdUI` obiektu będzie równa null.

Pozwala to na włączenie menu podręcznego w odróżnieniu od elementów menu, ale wymaga napisania kodu z obsługą menu. Na przykład w menu zagnieżdżonym o następującej strukturze:

```Output
File>
    New>
    Sheet (ID_NEW_SHEET)
    Chart (ID_NEW_CHART)
```

Polecenia ID_NEW_SHEET i ID_NEW_CHART mogą być niezależnie włączone lub wyłączone. **Nowe** menu podręczne powinno być włączone, jeśli jest włączona jedna z dwóch.

Procedura obsługi poleceń dla ID_NEW_SHEET (pierwsze polecenie w wyskakującym okienku) będzie wyglądać następująco:

```cpp
void CMyApp::OnUpdateNewSheet(CCmdUI* pCmdUI)
{
    if (pCmdUI->m_pSubMenu != NULL)
    {
        // enable entire pop-up for "New" sheet and chart
        BOOL bEnable = m_bCanCreateSheet || m_bCanCreateChart;
        // CCmdUI::Enable is a no-op for this case, so we
        // must do what it would have done.
        pCmdUI->m_pMenu->EnableMenuItem(pCmdUI->m_nIndex,
            MF_BYPOSITION |
            (bEnable  MF_ENABLED : (MF_DISABLED | MF_GRAYED)));

        return;
    }
    // otherwise just the New Sheet command
    pCmdUI->Enable(m_bCanCreateSheet);
}
```

Procedura obsługi poleceń dla ID_NEW_CHART będzie normalną procedurą obsługi poleceń aktualizacji i wygląda następująco:

```cpp
void CMyApp::OnUpdateNewChart(CCmdUI* pCmdUI)
{
    pCmdUI->Enable(m_bCanCreateChart);
}
```

## <a name="on_command-and-on_bn_clicked"></a>ON_COMMAND i ON_BN_CLICKED

Makra mapy komunikatów dla **ON_COMMAND** i **ON_BN_CLICKED** są takie same. Mechanizm routingu powiadomień polecenia MFC i kontroli używa tylko identyfikatora polecenia, aby określić, gdzie ma być kierowany. Powiadomienia sterujące z kodem powiadomień o wartości zero (**BN_CLICKED**) są interpretowane jako polecenia.

> [!NOTE]
> W rzeczywistości wszystkie komunikaty powiadomień sterowania przechodzą przez łańcuch obsługi poleceń. Na przykład jest technicznie możliwe, aby można było napisać procedurę obsługi powiadomień kontrolki dla **EN_CHANGE** w klasie dokumentu. Nie jest to ogólnie zalecane, ponieważ praktyczne aplikacje tej funkcji są nieobsługiwane przez ClassWizard, a korzystanie z funkcji może spowodować delikatny kod.

## <a name="disabling-the-automatic-disabling-of-button-controls"></a>Wyłączanie automatycznego wyłączania kontrolek przycisków

Jeśli umieścisz kontrolkę przycisku na pasku dialogowym lub w oknie dialogowym, przy użyciu którego wywołujesz **CWnd:: UpdateDialogControls** , zobaczysz, że przyciski, które nie mają programów **ON_COMMAND** lub **ON_UPDATE_COMMAND_UI** , zostaną automatycznie wyłączone przez platformę. W niektórych przypadkach nie trzeba mieć programu obsługi, ale przycisk ma pozostać włączony. Najprostszym sposobem osiągnięcia tego celu jest dodanie fikcyjnej procedury obsługi polecenia (łatwy do wykonania z ClassWizard) i nic nie rób.

## <a name="window-message-routing"></a>Routing komunikatów okna

Poniżej opisano niektóre bardziej zaawansowane tematy dotyczące klas MFC oraz sposób ich działania w ramach routingu komunikatów systemu Windows i innych tematów. Informacje w tym miejscu są opisane tylko krótko. Szczegółowe informacje na temat publicznych interfejsów API można znaleźć w *dokumentacji biblioteki klas* . Aby uzyskać więcej informacji na temat szczegółów implementacji, zapoznaj się z kodem źródłowym biblioteki MFC.

Aby uzyskać szczegółowe informacje na temat oczyszczania okna, należy zapoznać się z [uwagami technicznymi](../mfc/tn017-destroying-window-objects.md) dotyczącymi wszystkich klas pochodnych **CWnd**.

## <a name="cwnd-issues"></a>CWnd problemy

Implementacja funkcji składowej **CWnd:: OnChildNotify** zapewnia zaawansowaną i rozszerzalną architekturę okien podrzędnych (nazywanych również kontrolkami) do haka lub w inny sposób informowanie o komunikatach, poleceniach i powiadomieniach o kontrolkach, które przechodzą do ich rodzica (lub "właściciel"). Jeśli okno podrzędne (/Control) jest obiektem języka C++ **CWnd** , funkcja wirtualna **OnChildNotify** jest wywoływana najpierw z parametrami z oryginalnej wiadomości (czyli strukturą **komunikatów** ). Okno podrzędne może opuścić komunikat, Eat lub zmodyfikować komunikat dla elementu nadrzędnego (rzadki).

Domyślna implementacja **CWnd** obsługuje następujące komunikaty i używa punktu zaczepienia **OnChildNotify** , aby zezwolić podrzędnym systemom Windows (kontrolki) na pierwszy dostęp w komunikacie:

- **WM_MEASUREITEM** i **WM_DRAWITEM** (dla samorysowania)

- **WM_COMPAREITEM** i **WM_DELETEITEM** (dla samorysowania)

- **WM_HSCROLL** i **WM_VSCROLL**

- **WM_CTLCOLOR**

- **WM_PARENTNOTIFY**

Zauważysz, że hak **OnChildNotify** służy do zmiany komunikatów rysowanych przez właściciela w wiadomościach samodzielnych.

Oprócz punktu zaczepienia **OnChildNotify** komunikaty przewijania mają dalsze zachowanie routingu. Więcej informacji na temat pasków przewijania i źródeł **WM_HSCROLL** i komunikatów **WM_VSCROLL** można znaleźć poniżej.

## <a name="cframewnd-issues"></a>Obiektu CFrameWnd problemy

Klasa **obiektu CFrameWnd** zawiera większość poleceń routingu i interfejsu użytkownika. Jest to używane głównie dla głównego okna ramowego aplikacji (**CWinApp:: m_pMainWnd**), ale ma zastosowanie do wszystkich okien ramowych.

Okno głównej ramki jest oknem z paskiem menu i jest elementem nadrzędnym paska stanu lub wiersza wiadomości. Zapoznaj się z powyższą dyskusją dotyczącą routingu poleceń i **WM_INITMENUPOPUP.**

Klasa **obiektu CFrameWnd** umożliwia zarządzanie aktywnym widokiem. Następujące komunikaty są kierowane przez aktywny widok:

- Wszystkie komunikaty poleceń (aktywny widok uzyskują pierwszy dostęp do nich).

- **WM_HSCROLL** i **WM_VSCROLL** komunikatów z pasków przewijania elementów równorzędnych (patrz poniżej).

- **WM_ACTIVATE** (i **WM_MDIACTIVATE** dla MDI) są włączone wywołania funkcji wirtualnej **CView:: OnActivateView**.

## <a name="cmdiframewndcmdichildwnd-issues"></a>Problemy z CMDIFrameWnd/CMDIChildWnd

Obie klasy okna ramki MDI pochodzą z **obiektu CFrameWnd** i w związku z tym są włączone dla tego samego sortowania poleceń i aktualizacji interfejsu użytkownika, które są dostępne w **obiektu CFrameWnd**. W typowej aplikacji MDI tylko główne okno ramek (czyli obiekt **CMDIFrameWnd** ) utrzymuje pasek menu i pasek stanu, dlatego jest głównym źródłem implementacji poleceń routingu.

Ogólnym schematem routingu jest to, że aktywne okno podrzędne MDI uzyskuje pierwszy dostęp do poleceń. Domyślne funkcje **PreTranslateMessage** obsługują tabele akceleratorów dla okien podrzędnych MDI (pierwszy) i ramki MDI (sekundę), a także standardowe akceleratory poleceń systemu MDI zwykle obsługiwane przez **TranslateMDISysAccel** (Last).

## <a name="scroll-bar-issues"></a>Problemy z paskiem przewijania

Podczas obsługi funkcji Scroll-Message (**WM_HSCROLL** / **OnHScroll** i/lub **WM_VSCROLL** / **OnVScroll**) należy spróbować napisać kod programu obsługi, aby nie zależeć od lokalizacji, z której pochodzi komunikat paska przewijania. Jest to nie tylko ogólny problem z systemem Windows, ponieważ komunikaty przewijania mogą pochodzić z rzeczywistych kontrolek paska przewijania lub z **WS_HSCROLL** / **WS_VSCROLL** paski przewijania, które nie są kontrolkami paska przewijania.

MFC rozszerza, że aby kontrolki paska przewijania były elementami podrzędnymi lub równorzędnymi przewinięcie okna (w rzeczywistości relacja nadrzędny/podrzędny między paskiem przewijania i przewijanym oknem może mieć dowolną wartość). Jest to szczególnie ważne w przypadku współużytkowanych pasków przewijania z oknami rozdzielacza. Zapoznaj się z [uwagą techniczną 29](../mfc/tn029-splitter-windows.md) , aby zapoznać się ze szczegółami dotyczącymi implementacji **CSplitterWnd** , w tym więcej informacji na temat udostępnionych problemów z paskiem przewijania.

Na notatce bocznej istnieją dwie klasy pochodne **CWnd** , w których style paska przewijania określone w czasie tworzenia są zalewkowane i nie są przesyłane do systemu Windows. Po przekazaniu do procedury tworzenia **WS_HSCROLL** i **WS_VSCROLL** można niezależnie ustawić, ale po utworzeniu nie można zmienić. Oczywiście nie należy bezpośrednio testować ani ustawiać WS_SCROLLych bitów stylu utworzonego okna.

Dla **CMDIFrameWnd** style paska przewijania, które są przekazywane do **tworzenia** lub **LOADFRAME** są używane do tworzenia MDICLIENT. Jeśli chcesz mieć przewijany obszar MDICLIENT (taki jak Menedżer programu Windows), upewnij się, że ustawisz oba style paska przewijania (**WS_HSCROLL** &#124; **WS_VSCROLL**) dla stylu używanego do tworzenia **CMDIFrameWnd**.

Dla **CSplitterWnd** style paska przewijania mają zastosowanie do specjalnych udostępnionych pasków przewijania dla regionów rozdzielacza. W przypadku statycznych okien rozdzielacza zwykle nie ustawisz stylu paska przewijania. W przypadku dynamicznych okien rozdzielacza zwykle jest ustawiony styl paska przewijania dla kierunku, który będzie dzielony, czyli **WS_HSCROLL** , jeśli można podzielić wiersze, **WS_VSCROLL** , jeśli można podzielić kolumny.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
