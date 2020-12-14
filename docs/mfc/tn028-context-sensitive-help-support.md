---
description: 'Dowiedz się więcej na temat: TN028: Context-Sensitive pomocy technicznej'
title: 'TN028: obsługa pomocy kontekstowej'
ms.date: 11/04/2016
f1_keywords:
- vc.help
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
ms.openlocfilehash: 96dd1d4356ac226d9377e14985de46e3d0f680ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215654"
---
# <a name="tn028-context-sensitive-help-support"></a>TN028: obsługa pomocy kontekstowej

Ta Uwaga opisuje reguły przypisywania kontekstów pomocy i innych problemów pomocy w MFC. Obsługa pomocy kontekstowej wymaga kompilatora pomocy, który jest dostępny w Visual C++.

> [!NOTE]
> Oprócz implementacji pomocy kontekstowej przy użyciu programu WinHelp, MFC obsługuje również korzystanie z pomocy HTML. Aby uzyskać więcej informacji na temat pomocy technicznej i programowania za pomocą języka HTML, zobacz [Pomoc HTML: Context-Sensitive pomocy dla programów](../mfc/html-help-context-sensitive-help-for-your-programs.md).

## <a name="types-of-help-supported"></a>Obsługiwane typy pomocy

Istnieją dwa typy pomocy kontekstowej zaimplementowane w aplikacjach systemu Windows. Pierwsze, zwane "F1 Help" obejmuje Uruchamianie programu WinHelp z odpowiednim kontekstem opartym na aktualnie aktywnym obiekcie. Drugim jest tryb "Shift + F1". W tym trybie kursor myszy zmienia się w kursor pomocy, a użytkownik będzie kontynuował kliknięcie obiektu. W tym momencie zostanie uruchomiony program WinHelp, aby uzyskać pomoc dotyczącą obiektu, który został kliknięty przez użytkownika.

Microsoft Foundation Classes zaimplementować obie te formy pomocy. Ponadto platforma obsługuje dwa proste polecenia pomocy, indeksowanie i korzystanie z pomocy.

## <a name="help-files"></a>Pliki pomocy

Klasy Microsoft Foundation zakładają pojedynczy plik pomocy. Ten plik pomocy musi mieć taką samą nazwę i ścieżkę co aplikacja. Na przykład, jeśli plik wykonywalny jest C:\MyApplication\MyHelp.exe plik pomocy musi być C:\MyApplication\MyHelp.hlp. Ścieżka jest ustawiana za pomocą zmiennej składowej *M_pszHelpFilePath* [klasy CWinApp](../mfc/reference/cwinapp-class.md).

## <a name="help-context-ranges"></a>Zakresy kontekstu pomocy

Domyślna implementacja MFC wymaga, aby program przestrzegał niektórych reguł dotyczących przypisania identyfikatorów kontekstu pomocy. Te reguły są zakresem identyfikatorów przypisanym do określonych kontrolek. Te reguły można zastąpić, dostarczając różne implementacje różnych funkcji składowych powiązanych z pomocą.

```
0x00000000 - 0x0000FFFF : user defined
0x00010000 - 0x0001FFFF : commands (menus/command buttons)
0x00010000 + ID_
(note: 0x18000-> 0x1FFFF is the practical range since command IDs are>=0x8000)
0x00020000 - 0x0002FFFF : windows and dialogs
0x00020000 + IDR_
(note: 0x20000-> 0x27FFF is the practical range since IDRs are <= 0x7FFF)
0x00030000 - 0x0003FFFF : error messages (based on error string ID)
0x00030000 + IDP_
0x00040000 - 0x0004FFFF : special purpose (non-client areas)
0x00040000 + HitTest area
0x00050000 - 0x0005FFFF : controls (those that are not commands)
0x00040000 + IDW_
```

## <a name="simple-help-commands"></a>Proste polecenia "pomoc"

Istnieją dwa proste polecenia pomocy, które są implementowane przez Microsoft Foundation Classes:

- ID_HELP_INDEX, który jest implementowany przez [CWinApp:: OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)

- ID_HELP_USING, który jest implementowany przez [CWinApp:: OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)

Pierwsze polecenie pokazuje indeks pomocy dla aplikacji. Drugi pokazuje pomoc użytkownika dotyczącą korzystania z programu WinHelp.

## <a name="context-sensitive-help-f1-help"></a>Pomoc Context-Sensitive (Pomoc F1)

Klawisz F1 jest zazwyczaj tłumaczony na polecenie o IDENTYFIKATORze ID_HELP przez akcelerator umieszczony w tabeli akceleratora okna głównego. Polecenie ID_HELP może być również generowane przez przycisk o IDENTYFIKATORze ID_HELP w oknie głównym lub oknie dialogowym.

Niezależnie od tego, jak generowane jest polecenie ID_HELP, jest ono kierowane jako normalne polecenie do momentu, aż osiągnie procedurę obsługi polecenia. Aby uzyskać więcej informacji na temat architektury routingu poleceń MFC, zapoznaj się z [uwagą techniczną 21](../mfc/tn021-command-and-message-routing.md). Jeśli aplikacja ma włączoną pomoc, polecenie ID_HELP będzie obsługiwane przez [CWinApp:: OnHelp](../mfc/reference/cwinapp-class.md#onhelp). Obiekt application odbiera komunikat pomocy, a następnie kieruje odpowiednie polecenie. Jest to konieczne, ponieważ domyślne kierowanie poleceń nie jest wystarczające do określenia najbardziej określonego kontekstu.

`CWinApp::OnHelp` podejmuje próbę uruchomienia programu WinHelp w następującej kolejności:

1. Sprawdza, czy aktywne `AfxMessageBox` wywołanie ma identyfikator pomocy. Jeśli okno komunikatu jest aktualnie aktywne, zostanie uruchomiony program WinHelp z kontekstem odpowiednim dla tego okna komunikatu.

1. Wysyła komunikat WM_COMMANDHELP do aktywnego okna. Jeśli to okno nie odpowiada przez uruchomienie programu WinHelp, ten sam komunikat jest wysyłany do elementów nadrzędnych tego okna do momentu przetworzenia komunikatu lub bieżącego okna jest oknem najwyższego poziomu.

1. Wysyła polecenie ID_DEFAULT_HELP do okna głównego. Powoduje to wywołanie domyślnej pomocy. To polecenie jest zazwyczaj mapowane na `CWinApp::OnHelpIndex` .

Aby globalnie zastąpić domyślne wartości identyfikatora domyślnego (np. 0x10000 dla poleceń i 0x20000 dla zasobów, takich jak okna dialogowe), aplikacja powinna zastąpić [CWinApp:: WinHelp](../mfc/reference/cwinapp-class.md#winhelp).

Aby przesłonić tę funkcję i sposób określania kontekstu pomocy, należy obsłużyć WM_COMMANDHELP komunikat. Warto podać bardziej specyficzny Routing pomocy niż w przypadku platformy, ponieważ jest ona przemieszczona tylko jako bieżące okno podrzędne MDI. Warto również udostępnić bardziej szczegółową pomoc dla określonego okna lub okna dialogowego, na przykład w zależności od bieżącego stanu wewnętrznego tego obiektu lub aktywnej kontrolki w oknie dialogowym.

## <a name="wm_commandhelp"></a>WM_COMMANDHELP

```

afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)
```

WM_COMMANDHELP to prywatny komunikat systemu Windows MFC odbierany przez aktywne okno, gdy zażądano pomocy. Gdy okno otrzyma ten komunikat, może wywołać `CWinApp::WinHelp` kontekst, który jest zgodny ze stanem wewnętrznym okna.

*lParam*<br/>
Zawiera aktualnie dostępny kontekst pomocy. *lParam* jest równa zero, jeśli nie został określony żaden kontekst pomocy. Implementacja programu `OnCommandHelp` może używać identyfikatora kontekstu w *lParam* do określenia innego kontekstu lub po prostu przekazać go do `CWinApp::WinHelp` .

*wParam*<br/>
Nie jest używana i będzie równa zero.

Jeśli `OnCommandHelp` funkcja wywołuje `CWinApp::WinHelp` , powinna zwracać **wartość true**. Zwrócenie **wartości true** powoduje zatrzymanie routingu tego polecenia do innych klas i do innych okien.

## <a name="help-mode-shiftf1-help"></a>Tryb pomocy (pomoc Shift + F1)

Jest to druga forma pomocy kontekstowej. Na ogół ten tryb jest wprowadzany przez naciśnięcie klawiszy SHIFT + F1 lub menu/paska narzędzi. Jest zaimplementowana jako polecenie (ID_CONTEXT_HELP). Hak filtru komunikatów nie jest używany do tłumaczenia tego polecenia, gdy modalne okno dialogowe lub menu jest aktywne, dlatego to polecenie jest dostępne tylko dla użytkownika, gdy aplikacja wykonuje główną pompę komunikatów ( `CWinApp::Run` ).

Po wprowadzeniu tego trybu wskaźnik myszy pomocy jest wyświetlany na wszystkich obszarach aplikacji, nawet jeśli w aplikacji normalnie zostanie wyświetlony własny kursor dla tego obszaru (na przykład obramowanie zmiany rozmiarów wokół okna). Użytkownik może użyć myszy lub klawiatury, aby wybrać polecenie. Zamiast wykonywania polecenia, zostanie wyświetlona Pomoc dotycząca tego polecenia. Ponadto użytkownik może kliknąć widoczny obiekt na ekranie, na przykład przycisk na pasku narzędzi, i wyświetlić pomoc dla tego obiektu. Ten tryb pomocy jest dostępny w programie `CWinApp::OnContextHelp` .

Podczas wykonywania tej pętli wszystkie dane wejściowe z klawiatury są nieaktywne, z wyjątkiem kluczy, które uzyskują dostęp do tego menu. Ponadto tłumaczenie poleceń jest nadal wykonywane przez program, `PreTranslateMessage` Aby umożliwić użytkownikowi naciśnięcie klawisza skrótu i otrzymywanie pomocy dotyczącej tego polecenia.

Jeśli istnieją określone tłumaczenia lub akcje wykonywane w `PreTranslateMessage` funkcji, która nie powinna być wykonywana w trybie pomocy Shift + F1,  `CWinApp` przed wykonaniem tych operacji należy sprawdzić m_bHelpMode członkiem. `CDialog`Implementacja `PreTranslateMessage` tego sprawdzenia przed wywołaniem `IsDialogMessage` , na przykład. Wyłącza to klucze "Nawigacja okna dialogowego" w niemodalnych oknach dialogowych w trybie SHIFT + F1. Ponadto `CWinApp::OnIdle` jest nadal wywoływana w tej pętli.

Jeśli użytkownik wybierze polecenie z menu, jest ono obsługiwane jako pomoc dla tego polecenia (do WM_COMMANDHELP, patrz poniżej). Jeśli użytkownik kliknie widoczny obszar okna aplikacje, oznacza to, że jest to nieklienckie kliknięcie lub kliknięcie przez klienta. `OnContextHelp` obsługuje mapowanie kliknięć nieklienckiej do kliknięć przez klienta automatycznie. W przypadku kliknięcia klienta klient wysyła WM_HELPHITTEST do okna, które zostało kliknięte. Jeśli to okno zwróci wartość różną od zera, ta wartość jest używana jako kontekst pomocy. Jeśli zwróci zero, program `OnContextHelp` próbuje okno nadrzędne (i niepowodzenie, jego element nadrzędny itd.). Jeśli nie można określić kontekstu pomocy, domyślnie wysyła polecenie ID_DEFAULT_HELP do okna głównego, które jest następnie (zazwyczaj) mapowane na `CWinApp::OnHelpIndex` .

## <a name="wm_helphittest"></a>WM_HELPHITTEST

```

afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)
```

WM_HELPHITTEST to prywatny komunikat systemu Windows (MFC) odbierany przez aktywne okno kliknięte w trybie pomocy SHIFT + F1. Gdy okno otrzyma ten komunikat, zwraca identyfikator pomocy **typu DWORD** , który będzie używany przez program WinHelp.

LOWORD (lParam) zawiera współrzędną urządzenia osi X, w której kliknięto mysz względem obszaru klienckiego okna.

HIWORD (lParam) zawiera współrzędną oś Y.

*wParam*<br/>
nie jest używana i będzie równa zero. Jeśli zwracana wartość jest różna od zera, WinHelp jest wywoływana z tym kontekstem. Jeśli wartością zwracaną jest zero, do okna nadrzędnego jest wysyłane zapytanie w celu uzyskania pomocy.

W wielu przypadkach można korzystać z kodu testowania trafień, który może już istnieć. Zapoznaj się z implementacją `CToolBar::OnHelpHitTest` dla przykładu obsługi komunikatu WM_HELPHITTEST (kod wykorzystuje kod testu trafień używany na przyciskach i etykietkach narzędzi w programie `CControlBar` ).

## <a name="mfc-application-wizard-support-and-makehm"></a>Obsługa Kreatora aplikacji MFC i MAKEHM

Kreator aplikacji MFC tworzy pliki niezbędne do skompilowania pliku pomocy (pliki. CNT i. hpj). Zawiera również kilka wstępnie skompilowanych plików RTF, które są akceptowane przez kompilator pomocy firmy Microsoft. Wiele tematów zostało ukończonych, ale niektóre mogą wymagać modyfikacji dla konkretnej aplikacji.

Automatyczne tworzenie pliku "Help Mapping" jest obsługiwane przez narzędzie o nazwie MAKEHM. Narzędzie MAKEHM może przetłumaczyć zasób aplikacji. H plik do mapowania pomocy. Na przykład:

```
#define IDD_MY_DIALOG   2000
#define ID_MY_COMMAND   150
```

zostanie przetłumaczony na:

```
HIDD_MY_DIALOG    0x207d0
HID_MY_COMMAND    0x10096
```

Ten format jest zgodny z funkcją kompilatora pomocy, która mapuje identyfikatory kontekstu (numery po prawej stronie) o nazwy tematów (symbole po lewej stronie).

Kod źródłowy dla MAKEHM jest dostępny w przykładowym narzędziu programistycznym MFC [MAKEHM](../overview/visual-cpp-samples.md).

## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>Dodawanie pomocy technicznej po uruchomieniu Kreatora aplikacji MFC

Najlepszym sposobem na dodanie pomocy do aplikacji jest sprawdzenie opcji "Pomoc kontekstowa" na stronie funkcje zaawansowane Kreatora aplikacji MFC przed utworzeniem aplikacji. Dzięki temu Kreator aplikacji MFC automatycznie dodaje niezbędne wpisy mapy komunikatów do `CWinApp` klasy pochodnej, aby zapewnić pomoc techniczną.

## <a name="help-on-message-boxes"></a>Pomoc dotycząca okien komunikatów

Pomoc dotycząca okien komunikatów (czasami nazywanych alertami) jest obsługiwana przez `AfxMessageBox` funkcję, otokę dla `MessageBox` interfejsu API systemu Windows.

Istnieją dwie wersje `AfxMessageBox` , jeden do użycia z identyfikatorem ciągu i drugi do użycia ze wskaźnikiem do ciągu ( `LPCSTR` ):

```
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```

W obu przypadkach istnieje opcjonalny identyfikator pomocy.

W pierwszym przypadku wartość domyślna dla nIDHelp jest równa 0, co oznacza brak pomocy dla tego okna komunikatu. Jeśli użytkownik naciśnie klawisz F1, na przykład okno komunikatu jest aktywne, użytkownik nie będzie otrzymywać pomocy (nawet jeśli aplikacja obsługuje pomoc). Jeśli nie jest to pożądane, należy podać identyfikator pomocy dla nIDHelp.

W drugim przypadku wartość domyślna nIDHelp to-1, co oznacza, że identyfikator pomocy jest taki sam jak nIDPrompt. Pomoc będzie działała tylko wtedy, gdy aplikacja jest w toku. Jeśli chcesz, aby okno komunikatu nie obsługiwało pomocy, należy podać wartość 0 dla nIDHelp. Jeśli chcesz, aby komunikat był pomocny, ale potrzebujesz innego identyfikatora pomocy niż nIDPrompt, po prostu podaj wartość dodatnią dla nIDHelp innego niż nIDPrompt.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
