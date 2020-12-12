---
description: 'Dowiedz się więcej o: TN022: implementacja poleceń standardowych'
title: 'TN022: implementacja poleceń standardowych'
ms.date: 11/04/2016
f1_keywords:
- vc.commands
helpviewer_keywords:
- ID_PREV_PANE command [MFC]
- ID_APP_EXIT command [MFC]
- ID_NEXT_PANE command [MFC]
- ID_INDICATOR_REC command [MFC]
- ID_WINDOW_SPLIT command [MFC]
- ID_FILE_PRINT_PREVIEW command [MFC]
- ID_WINDOW_CASCADE command [MFC]
- ID_FILE_CLOSE command [MFC]
- ID_FILE_SAVE_COPY_AS command [MFC]
- ID_WINDOW_ARRANGE command [MFC]
- ID_EDIT_FIND command [MFC]
- ID_FILE_OPEN command [MFC]
- ID_FILE_PAGE_SETUP command [MFC]
- ID_OLE_VERB_FIRST command [MFC]
- ID_EDIT_UNDO command [MFC]
- ID_EDIT_CLEAR command [MFC]
- ID_INDICATOR_CAPS command [MFC]
- ID_HELP_INDEX command [MFC]
- commands [MFC], standard
- ID_FILE_PRINT_SETUP command [MFC]
- ID_DEFAULT_HELP command [MFC]
- ID_INDICATOR_SCRL command [MFC]
- ID_FILE_PRINT command [MFC]
- ID_INDICATOR_OVR command [MFC]
- ID_INDICATOR_KANA command [MFC]
- ID_EDIT_COPY command [MFC]
- ID_EDIT_REDO command [MFC]
- ID_EDIT_PASTE command [MFC]
- ID_OLE_INSERT_NEW command [MFC]
- ID_OLE_EDIT_LINKS command [MFC]
- ID_EDIT_PASTE_SPECIAL command [MFC]
- ID_INDICATOR_EXT command [MFC]
- ID_HELP_USING command [MFC]
- standard commands
- ID_VIEW_STATUS_BAR command [MFC]
- ID_FILE_SAVE_AS command [MFC]
- ID_EDIT_CLEAR_ALL command [MFC]
- ID_WINDOW_NEW command [MFC]
- ID_CONTEXT_HELP command [MFC]
- ID_EDIT_REPLACE command [MFC]
- ID_WINDOW_TILE_HORZ command [MFC]
- ID_APP_ABOUT command [MFC]
- TN022
- ID_VIEW_TOOLBAR command [MFC]
- ID_HELP command [MFC]
- ID_WINDOW_TILE_VERT command [MFC]
- ID_EDIT_CUT command [MFC]
- ID_FILE_UPDATE command [MFC]
- ID_EDIT_REPEAT command [MFC]
- ID_FILE_SAVE command [MFC]
- ID_EDIT_PASTE_LINK command [MFC]
- ID_EDIT_SELECT_ALL command [MFC]
- ID_FILE_NEW command [MFC]
- ID_INDICATOR_NUM command
ms.assetid: a7883b46-23f7-4870-ac3a-804aed9258b5
ms.openlocfilehash: 7c8540dcf0e41e5f6d5f00a4f22568c4df0fcdbe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215810"
---
# <a name="tn022-standard-commands-implementation"></a>TN022: implementacja poleceń standardowych

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga zawiera opis standardowych implementacji poleceń zapewnianych przez MFC 2,0. Przeczytaj najpierw [uwagę techniczną 21](../mfc/tn021-command-and-message-routing.md) , ponieważ opisuje ona mechanizmy używane do implementowania wielu standardowych poleceń.

W tym opisie założono znajomość architektur MFC, interfejsów API i wspólnych rozwiązań programistycznych. Opisane są również interfejsy API "tylko implementacji". Nie jest to miejsce, w którym można zacząć uczenie się na temat funkcji lub sposobu programowania w MFC. Zapoznaj się z Visual C++, aby uzyskać więcej ogólnych informacji oraz szczegóły udokumentowanych interfejsów API.

## <a name="the-problem"></a>Problem

MFC definiuje wiele standardowych identyfikatorów poleceń w pliku nagłówkowym plik AFXRES. H. Obsługa tych poleceń przez platformę jest różna. Informacje o tym, gdzie i jak klasy struktury obsługują te polecenia, nie tylko pokazują, jak działa platforma wewnętrznie, ale udostępnia przydatne informacje na temat sposobu dostosowywania standardowych implementacji i pouczenia się kilku technik wdrażania własnych programów obsługi poleceń.

## <a name="contents-of-this-technical-note"></a>Zawartość tej uwagi technicznej

Każdy identyfikator polecenia jest opisany w dwóch sekcjach:

- Title: Nazwa symboliczna identyfikatora polecenia (na przykład ID_FILE_SAVE), a następnie przeznaczenie polecenia (na przykład "zapisuje bieżący dokument") oddzielone dwukropkiem.

- Jeden lub więcej akapitów opisujących, które klasy implementują polecenie i jakie są implementacje domyślne

Większość domyślnych implementacji poleceń jest przednich w mapie komunikatów klasy podstawowej platformy. Istnieją pewne implementacje poleceń, które wymagają jawnej okablowania w klasie pochodnej. Opisano je w sekcji "Uwaga". W przypadku wybrania odpowiednich opcji w programie AppWizard te domyślne programy obsługi zostaną połączone dla Ciebie w wygenerowanej aplikacji szkieletowej.

## <a name="naming-convention"></a>Konwencje nazewnictwa

Standardowe polecenia są zgodne z prostą konwencją nazewnictwa, która zaleca się użyć, jeśli jest to możliwe. Większość standardowych poleceń znajduje się w standardowych miejscach na pasku menu aplikacji. Nazwa symboliczna polecenia rozpoczyna się od "ID_", po którym następuje nazwa standardowego menu podręcznego, a następnie nazwa elementu menu. Nazwa symboliczna znajduje się w Wielkiej literze z podkreśleniem słowo-podział. Dla poleceń, które nie mają standardowych nazw elementów menu, jest definiowana nazwa polecenia logicznego rozpoczynająca się od "ID_" (na przykład ID_NEXT_PANE).

Prefiks "ID_" jest używany do wskazywania poleceń, które są przeznaczone do powiązania z elementami menu, przyciskami paska narzędzi lub innymi obiektami interfejsu użytkownika poleceń. Procedury obsługi poleceń obsługujące polecenia "ID_" powinny używać mechanizmów ON_COMMAND i ON_UPDATE_COMMAND_UI architektury poleceń MFC.

Zalecamy używanie standardowego prefiksu "IDM_" dla elementów menu, które nie są zgodne z architekturą poleceń i wymagają kodu specyficznego dla menu, aby je włączyć i wyłączyć. Oczywiście liczba poleceń specyficznych dla menu powinna być mała, ponieważ następująca architektura poleceń MFC nie tylko sprawia, że programy obsługi poleceń są bardziej wydajne (ponieważ będą działały z paskami narzędzi), ale umożliwią wielokrotne użycie kodu programu obsługi poleceń.

## <a name="id-ranges"></a>Zakresy identyfikatorów

Zapoznaj się z [uwagą techniczną 20](../mfc/tn020-id-naming-and-numbering-conventions.md) , aby uzyskać szczegółowe informacje na temat używania zakresów identyfikatorów w MFC.

Standardowe polecenia MFC mieszczą się w zakresie od 0xE000 do 0xEFFF. Nie należy polegać na określonych wartościach tych identyfikatorów, ponieważ mogą one ulec zmianie w przyszłych wersjach biblioteki.

Aplikacja powinna definiować swoje polecenia z zakresu od 0x8000 do 0xDFFF.

## <a name="standard-command-ids"></a>Identyfikatory poleceń standardowych

Dla każdego identyfikatora polecenia istnieje ciąg standardowego wiersza wiadomości, który można znaleźć w MONITach pliku. Zwrot. Identyfikator ciągu dla tego wiersza menu musi być taki sam jak w przypadku identyfikatora polecenia.

- ID_FILE_NEW powoduje utworzenie nowego/pustego dokumentu.

    > [!NOTE]
    >  Aby włączyć tę funkcję, należy połączyć ją z `CWinApp` mapą komunikatów klasy pochodnej.

   `CWinApp::OnFileNew` implementuje to polecenie w różny sposób w zależności od liczby szablonów dokumentów w aplikacji. Jeśli istnieje tylko jeden `CDocTemplate` , `CWinApp::OnFileNew` program utworzy nowy dokument tego typu, a także odpowiednią klasę Frame i View.

   Jeśli jest więcej niż jeden `CDocTemplate` , `CWinApp::OnFileNew` zostanie wyświetlony monit o podanie użytkownikowi okna dialogowego (AFX_IDD_NEWTYPEDLG), które umożliwia im wybranie typu dokumentu do użycia. Wybrany element służy `CDocTemplate` do tworzenia dokumentu.

   Jednym z typowych dostosowań ID_FILE_NEW jest zapewnienie innego i większej liczby typów dokumentów. W takim przypadku można zaimplementować własny `CMyApp::OnFileNew` i umieścić go na mapie wiadomości zamiast `CWinApp::OnFileNew` . Nie ma potrzeby wywoływania implementacji klasy podstawowej.

   Innym typowym przystosowaniem ID_FILE_NEW jest udostępnienie oddzielnego polecenia do tworzenia dokumentu każdego typu. W takim przypadku należy zdefiniować nowe identyfikatory poleceń, na przykład ID_FILE_NEW_CHART i ID_FILE_NEW_SHEET.

- ID_FILE_OPEN otwiera istniejący dokument.

    > [!NOTE]
    >  Aby włączyć tę funkcję, należy połączyć ją z `CWinApp` mapą komunikatów klasy pochodnej.

   `CWinApp::OnFileOpen` ma bardzo prostą implementację wywołania, `CWinApp::DoPromptFileName` a po nim `CWinApp::OpenDocumentFile` Nazwa pliku lub ścieżki pliku do otwarcia. `CWinApp`Procedura implementacji `DoPromptFileName` wywołuje standardowe okno dialogowe FileOpen i wypełnia je rozszerzeniami plików uzyskanymi z bieżących szablonów dokumentów.

   Jednym z typowych dostosowań ID_FILE_OPEN jest dostosowanie okna dialogowego FileOpen lub dodanie dodatkowych filtrów plików. Zalecanym sposobem dostosowania jest zastąpienie domyślnej implementacji przy użyciu własnego okna dialogowego FileOpen i wywołanie `CWinApp::OpenDocumentFile` z nazwą pliku lub ścieżką dokumentu. Nie ma potrzeby wywoływania klasy bazowej.

- ID_FILE_CLOSE zamyka aktualnie otwarty dokument.

   `CDocument::OnFileClose` wywołania, `CDocument::SaveModified` Aby monitować użytkownika o zapisanie dokumentu, jeśli został on zmodyfikowany, a następnie jest wywoływany `OnCloseDocument` . Cała logika zamykająca, w tym niszczenie dokumentu, jest wykonywana w `OnCloseDocument` procedurze.

    > [!NOTE]
    >  ID_FILE_CLOSE działa inaczej niż komunikat WM_CLOSE lub polecenie systemu SC_CLOSE wysłane do okna ramki dokumentów. Zamknięcie okna spowoduje zamknięcie dokumentu tylko wtedy, gdy jest to ostatnie okno klatki pokazujące dokument. Zamknięcie dokumentu przy użyciu ID_FILE_CLOSE nie spowoduje zamknięcia dokumentu, ale spowoduje zamknięcie wszystkich okien ramowych pokazujących dokument.

- ID_FILE_SAVE zapisuje bieżący dokument.

   Implementacja używa procedury pomocnika `CDocument::DoSave` , która jest używana dla obu `OnFileSave` i `OnFileSaveAs` . Jeśli zapiszesz dokument, który nie został wcześniej zapisany (to oznacza, że nie ma on nazwy ścieżki, tak jak w przypadku FileNew) lub który został odczytany z dokumentu tylko do odczytu, `OnFileSave` logika będzie działać jak polecenie ID_FILE_SAVE_AS i poproszony o podanie nowej nazwy pliku. Rzeczywisty proces otwierania pliku i wykonywania operacji zapisywania odbywa się za pomocą funkcji wirtualnej `OnSaveDocument` .

   Istnieją dwie typowe przyczyny dostosowywania ID_FILE_SAVE. W przypadku dokumentów, które nie są zapisywane, po prostu usuń ID_FILE_SAVE elementy menu i przyciski paska narzędzi z interfejsu użytkownika. Upewnij się również, że dokument nie został zanieczyszczony (to oznacza, że nigdy nie jest wywoływana `CDocument::SetModifiedFlag` ), a platforma nie spowoduje zapisania dokumentu. W przypadku dokumentów, które są zapisywane w zwrócono komunikatu innym niż plik dysku, zdefiniuj nowe polecenie dla tej operacji.

   W przypadku `COleServerDoc` ID_FILE_SAVE jest używany zarówno do zapisywania plików (dla normalnych dokumentów), jak i do aktualizacji plików (dla dokumentów osadzonych).

   Jeśli dane dokumentu są przechowywane w poszczególnych plikach na dysku, ale nie chcesz używać domyślnej `CDocument` implementacji serializacji, należy przesłonić `CDocument::OnSaveDocument` zamiast `OnFileSave` .

- ID_FILE_SAVE_AS zapisuje bieżący dokument pod inną nazwą pliku.

   `CDocument::OnFileSaveAs`Implementacja używa tej samej `CDocument::DoSave` procedury pomocnika co `OnFileSave` . `OnFileSaveAs`Polecenie jest obsługiwane tak jak ID_FILE_SAVE, jeśli dokumenty nie miały nazwy pliku przed zapisem. `COleServerDoc::OnFileSaveAs` implementuje logikę w celu zapisania standardowego pliku danych dokumentu lub zapisania dokumentu serwera reprezentującego obiekt OLE osadzony w innej aplikacji jako oddzielny plik.

   W przypadku dostosowania logiki ID_FILE_SAVE prawdopodobnie zechcesz dostosować ID_FILE_SAVE_AS w podobny sposób lub operacja "Zapisz jako" nie ma zastosowania do dokumentu. Możesz usunąć element menu z paska menu, jeśli nie jest to potrzebne.

- ID_FILE_SAVE_COPY_AS zapisuje bieżący dokument z nową nazwą.

   `COleServerDoc::OnFileSaveCopyAs`Implementacja jest bardzo podobna do `CDocument::OnFileSaveAs` , z tą różnicą, że obiekt dokumentu nie jest "dołączony" do pliku bazowego po zapisaniu. Oznacza to, że jeśli dokument w pamięci był "zmodyfikowany" przed zapisem, nadal jest "zmodyfikowany". Ponadto to polecenie nie ma wpływu na nazwę ścieżki lub tytuł przechowywany w dokumencie.

- ID_FILE_UPDATE powiadamia kontener, aby zapisać osadzony dokument.

   `COleServerDoc::OnUpdateDocument`Implementacja po prostu powiadamia kontener o konieczności zapisania osadzania. Kontener następnie wywołuje odpowiednie interfejsy API OLE, aby zapisać osadzony obiekt.

- ID_FILE_PAGE_SETUP wywołuje okno dialogowe ustawień/układu strony specyficznej dla aplikacji.

   Obecnie nie ma żadnych standardowych dla tego okna dialogowego, a platforma nie ma domyślnej implementacji tego polecenia.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_FILE_PRINT_SETUP wywołać standardowego okna dialogowego konfiguracji wydruku.

    > [!NOTE]
    >  Aby włączyć tę funkcję, należy połączyć ją z `CWinApp` mapą komunikatów klasy pochodnej.

   To polecenie wywołuje standardowe okno dialogowe konfiguracji drukowania, które umożliwia użytkownikowi dostosowanie ustawień drukarki i drukowania dla co najmniej tego dokumentu lub dla wszystkich dokumentów w tej aplikacji. Aby zmienić domyślne ustawienia drukarki dla całego systemu, należy użyć panelu sterowania.

   `CWinApp::OnFilePrintSetup` ma bardzo prostą implementację tworzącą `CPrintDialog` obiekt i wywołując `CWinApp::DoPrintDialog` funkcję implementacji. Spowoduje to ustawienie domyślnej konfiguracji drukarki aplikacji.

   Typowym potrzebą dostosowania tego polecenia jest zezwolenie na ustawienia drukarki dla poszczególnych dokumentów, które powinny być przechowywane z dokumentem po jego zapisaniu. Aby to zrobić, należy dodać procedurę obsługi mapy komunikatów w klasie, `CDocument` która tworzy `CPrintDialog` obiekt, inicjuje ją z odpowiednimi atrybutami drukarki (zwykle *hDevMode* i *hDevNames*), wywołaj `CPrintDialog::DoModal` i zapisać zmienione ustawienia drukarki. Aby zapoznać się z niezawodną implementacją, należy zapoznać się z implementacją programu `CWinApp::DoPrintDialog` w celu wykrycia błędów oraz `CWinApp::UpdatePrinterSelection` w celu poradzenia sobie z prawidłowymi wartościami domyślnymi i śledzeniem zmian drukarki na poziomie systemu

- ID_FILE_PRINT drukowania standardowego bieżącego dokumentu

    > [!NOTE]
    >  Aby włączyć tę funkcję, należy połączyć ją z `CView` mapą komunikatów klasy pochodnej.

   To polecenie Drukuje bieżący dokument lub poprawnie uruchamia proces drukowania, który polega na wywołaniu standardowego okna dialogowego drukowania i uruchomieniu aparatu wydruku.

   `CView::OnFilePrint` implementuje to polecenie i główną pętlę drukowania. Wywołuje ona wirtualną, `CView::OnPreparePrinting` aby monitował użytkownika z oknem dialogowym drukowania. Następnie przygotuje wyjściowy kontroler domeny, aby przejść do drukarki, spowoduje wyświetlenie okna dialogowego postęp drukowania (AFX_IDD_PRINTDLG) i wysłanie `StartDoc` ucieczki do drukarki. `CView::OnFilePrint` zawiera również główną pętlę drukowania zorientowaną na strony. Dla każdej strony wywołuje wirtualną, a `CView::OnPrepareDC` następnie `StartPage` ucieczkę i wywołuje wirtualną `CView::OnPrint` dla tej strony. Po zakończeniu, wirtualna `CView::OnEndPrinting` jest wywoływana, a okno dialogowe postęp drukowania jest zamknięte.

   Architektura drukowania MFC została zaprojektowana tak, aby podpiąć wiele różnych sposobów drukowania i podglądu wydruku. Zwykle można znaleźć różne funkcje programu, które są `CView` odpowiednie dla wszystkich zadań drukowania zorientowanych na strony. W przypadku aplikacji, która korzysta z drukarki dla danych wyjściowych niezorientowanych na strony, należy znaleźć konieczność zastąpienia implementacji ID_FILE_PRINT.

- ID_FILE_PRINT_PREVIEW wejść w tryb podglądu wydruku dla bieżącego dokumentu.

    > [!NOTE]
    >  Aby włączyć tę funkcję, należy połączyć ją z `CView` mapą komunikatów klasy pochodnej.

   `CView::OnFilePrintPreview` uruchamia tryb podglądu wydruku, wywołując udokumentowaną funkcję pomocnika `CView::DoPrintPreview` . `CView::DoPrintPreview` jest głównym aparatem pętli podglądu wydruku, podobnie jak `OnFilePrint` główny aparat dla pętli drukowania.

   Operację podglądu wydruku można dostosować na wiele sposobów, przekazując różne parametry do `DoPrintPreview` . Zapoznaj się z [uwagami technicznymi 30](../mfc/tn030-customizing-printing-and-print-preview.md), które omawiają niektóre szczegóły dotyczące podglądu wydruku i sposobu ich dostosowywania.

- ID_FILE_MRU_FILE1... FILE16 zakres identyfikatorów poleceń dla **listy** MRU plików.

   `CWinApp::OnUpdateRecentFileMenu` jest programem obsługi interfejsu wiersza polecenia aktualizacji, który jest jednym z bardziej zaawansowanych sposobów korzystania z mechanizmu ON_UPDATE_COMMAND_UI. W zasobie menu należy zdefiniować tylko jeden element menu o IDENTYFIKATORze ID_FILE_MRU_FILE1. Ten element menu pozostaje początkowo wyłączony.

   W miarę zwiększania listy MRU elementy menu są dodawane do listy. Standardowa `CWinApp` implementacja domyślna to standardowy limit czterech ostatnio używanych plików. Można zmienić wartość domyślną, wywołując `CWinApp::LoadStdProfileSettings` z większą lub mniejszą wartością. Lista MRU jest przechowywana w aplikacji. Plik INI. Lista jest ładowana do funkcji aplikacji w `InitInstance` przypadku wywołania `LoadStdProfileSettings` i jest zapisywana po zakończeniu działania aplikacji. Procedura obsługi interfejsu wiersza polecenia aktualizacji MRU spowoduje również przekonwertowanie ścieżek bezwzględnych na ścieżki względne do wyświetlania w menu plik.

   `CWinApp::OnOpenRecentFile` jest programem obsługi ON_COMMAND, który wykonuje rzeczywiste polecenie. Po prostu Pobiera nazwę pliku z listy MRU i wywołuje `CWinApp::OpenDocumentFile` , która wykonuje wszystkie czynności otwierające plik i aktualizując listę MRU.

   Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_EDIT_CLEAR czyści bieżące zaznaczenie

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   `CEditView` zawiera implementację tego polecenia przy użyciu programu `CEdit::Clear` . Polecenie jest wyłączone, jeśli nie ma bieżącego wyboru.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_EDIT_CLEAR_ALL czyści cały dokument.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia. Zapoznaj się [z przykładowym samouczkiem dotyczącym](../overview/visual-cpp-samples.md) biblioteki MFC.

- ID_EDIT_COPY kopiuje bieżące zaznaczenie do Schowka.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   `CEditView` zawiera implementację tego polecenia, która kopiuje aktualnie zaznaczony tekst do Schowka jako CF_TEXT przy użyciu `CEdit::Copy` . Polecenie jest wyłączone, jeśli nie ma bieżącego wyboru.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_EDIT_CUT wycina bieżące zaznaczenie do Schowka.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   `CEditView` zawiera implementację tego polecenia, która wycina aktualnie zaznaczony tekst do Schowka jako CF_TEXT przy użyciu `CEdit::Cut` . Polecenie jest wyłączone, jeśli nie ma bieżącego wyboru.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_EDIT_FIND rozpoczyna operację znajdowania, powoduje wyświetlenie okna dialogowego Wyszukiwanie niemodalne.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   `CEditView` dostarcza implementację tego polecenia, która wywołuje funkcję pomocnika implementacji `OnEditFindReplace` i zapisuje poprzednie ustawienia znajdowania/zamieniania w prywatnych zmiennych implementacji. `CFindReplaceDialog`Klasa służy do zarządzania niemodalnym oknem dialogowym monitowania użytkownika.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_EDIT_PASTE Wstawia bieżącą zawartość schowka.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   `CEditView` zawiera implementację tego polecenia, która kopiuje bieżące dane w schowku zastępujące wybrany tekst przy użyciu `CEdit::Paste` . Polecenie jest wyłączone, jeśli w Schowku nie ma **CF_TEXT** .

   `COleClientDoc` po prostu udostępnia procedurę obsługi interfejsu wiersza polecenia aktualizacji dla tego polecenia. Jeśli Schowek nie zawiera osadzonego elementu/obiektu OLE, polecenie zostanie wyłączone. Użytkownik jest odpowiedzialny za pisanie procedury obsługi dla rzeczywistego polecenia, aby wykonać rzeczywiste wklejanie. Jeśli aplikacja OLE może również wkleić inne formaty, należy podać własny program obsługi interfejsu użytkownika poleceń aktualizacji w widoku lub dokumencie (to jest, w innym miejscu niż `COleClientDoc` w routingu docelowym polecenia).

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

   Do zastępowania standardowej implementacji OLE, użyj `COleClientItem::CanPaste` .

- ID_EDIT_PASTE_LINK wstawia łącze z bieżącej zawartości Schowka.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   `COleDocument` po prostu udostępnia procedurę obsługi interfejsu wiersza polecenia aktualizacji dla tego polecenia. Jeśli Schowek nie zawiera elementu/obiektu OLE do powiązania, polecenie zostanie wyłączone. Użytkownik jest odpowiedzialny za pisanie procedury obsługi dla rzeczywistego polecenia, aby wykonać rzeczywiste wklejanie. Jeśli aplikacja OLE może również wkleić inne formaty, należy podać własny program obsługi interfejsu użytkownika poleceń aktualizacji w widoku lub dokumencie (to jest, w innym miejscu niż `COleDocument` w routingu docelowym polecenia).

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

   Do zastępowania standardowej implementacji OLE, użyj `COleClientItem::CanPasteLink` .

- ID_EDIT_PASTE_SPECIAL Wstawia bieżącą zawartość schowka z opcjami.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej. MFC nie udostępnia tego okna dialogowego.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_EDIT_REPEAT powtarza ostatnią operację.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   `CEditView` dostarcza implementację tego polecenia, aby powtórzyć ostatnią operację znajdowania. Używane są prywatne zmienne implementacji dla ostatniego wyszukiwania. Polecenie jest wyłączone, jeśli nie można podjąć próby znalezienia.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_EDIT_REPLACE rozpoczyna operację zamiany, powoduje wyświetlenie okna dialogowego niemodalne zastąpienie.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   `CEditView` dostarcza implementację tego polecenia, która wywołuje funkcję pomocnika implementacji `OnEditFindReplace` i zapisuje poprzednie ustawienia znajdowania/zamieniania w prywatnych zmiennych implementacji. `CFindReplaceDialog`Klasa służy do zarządzania niemodalnym oknem dialogowym, które powoduje wyświetlenie odpowiedniego użytkownika.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_EDIT_SELECT_ALL wybiera cały dokument.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   `CEditView` zawiera implementację tego polecenia, która zaznacza cały tekst w dokumencie. Polecenie jest wyłączone, jeśli nie ma tekstu do wybrania.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_EDIT_UNDO Cofa ostatnią operację.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   `CEditView` zawiera implementację tego polecenia, używając polecenia `CEdit::Undo` . Polecenie jest wyłączone, jeśli `CEdit::CanUndo` zwraca wartość false.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_EDIT_REDO ponownie wykonuje ostatnią operację.

   Obecnie nie ma standardowej implementacji dla tego polecenia. Należy zaimplementować go dla każdej `CView` klasy pochodnej.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_WINDOW_NEW otwiera inne okno w aktywnym dokumencie.

   `CMDIFrameWnd::OnWindowNew` implementuje tę zaawansowaną funkcję przy użyciu szablonu dokumentu bieżącego dokumentu, aby utworzyć kolejną ramkę zawierającą inny widok bieżącego dokumentu.

   Podobnie jak w przypadku większości poleceń menu okien interfejsu (MDI), polecenie jest wyłączone, jeśli nie ma aktywnego okna podrzędnego MDI.

   Nie zaleca się dostosowywania tego programu obsługi poleceń. Jeśli chcesz podać polecenie, które tworzy dodatkowe widoki lub okna z ramkami, prawdopodobnie lepiej jest wyrównać własne polecenie. Można sklonować kod z `CMDIFrameWnd::OnWindowNew` i modyfikować go do konkretnej ramki i wyświetlać klasy swoich potrzeb.

- ID_WINDOW_ARRANGE rozmieszcza ikony w dolnej części okna MDI.

   `CMDIFrameWnd` implementuje to standardowe polecenie MDI w funkcji pomocnika implementacji `OnMDIWindowCmd` . Ten pomocnik mapuje identyfikatory poleceń na komunikaty MDI systemu Windows i w związku z tym może udostępniać wiele kodu.

   Podobnie jak w przypadku większości poleceń menu w oknie MDI polecenie jest wyłączone, jeśli nie ma aktywnego okna podrzędnego MDI.

   Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_WINDOW_CASCADE kaskaduje okna w taki sposób, że nakładają się na siebie.

   `CMDIFrameWnd` implementuje to standardowe polecenie MDI w funkcji pomocnika implementacji `OnMDIWindowCmd` . Ten pomocnik mapuje identyfikatory poleceń na komunikaty MDI systemu Windows i w związku z tym może udostępniać wiele kodu.

   Podobnie jak w przypadku większości poleceń menu w oknie MDI polecenie jest wyłączone, jeśli nie ma aktywnego okna podrzędnego MDI.

   Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_WINDOW_TILE_HORZ kafelków w poziomie.

   To polecenie jest zaimplementowane w `CMDIFrameWnd` taki sam sposób jak ID_WINDOW_CASCADE, z wyjątkiem tego, że dla operacji jest używany inny komunikat systemu Windows MDI.

   Należy wybrać domyślną orientację kafelka dla aplikacji. Można to zrobić, zmieniając identyfikator elementu menu "kafelek" okna na ID_WINDOW_TILE_HORZ lub ID_WINDOW_TILE_VERT.

- ID_WINDOW_TILE_VERT kafelków w pionie.

   To polecenie jest zaimplementowane w `CMDIFrameWnd` taki sam sposób jak ID_WINDOW_CASCADE, z wyjątkiem tego, że dla operacji jest używany inny komunikat systemu Windows MDI.

   Należy wybrać domyślną orientację kafelka dla aplikacji. Można to zrobić, zmieniając identyfikator elementu menu "kafelek" okna na ID_WINDOW_TILE_HORZ lub ID_WINDOW_TILE_VERT.

- ID_WINDOW_SPLIT interfejs klawiatury do rozdzielacza.

   `CView` obsługuje to polecenie dla `CSplitterWnd` implementacji. Jeśli widok jest częścią okna rozdzielacza, to polecenie zostanie delegowane do funkcji implementacji `CSplitterWnd::DoKeyboardSplit` . Spowoduje to umieszczenie rozdzielacza w trybie, który pozwoli użytkownikom klawiatury podzielić lub rozdzielić okno rozdzielacza.

   To polecenie jest wyłączone, jeśli widok nie znajduje się w rozdzielaczu.

   Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_APP_ABOUT wywołuje okno dialogowe informacje.

   Nie ma standardowej implementacji dla pola informacje o aplikacji. Domyślnie utworzona aplikacja AppWizard utworzy niestandardową klasę okna dialogowego dla aplikacji i użyje jej jako pola informacje. AppWizard również zapisze uproszczoną obsługę poleceń, która obsługuje to polecenie i wywołuje okno dialogowe.

   Niemal zawsze zaimplementujmy to polecenie.

- ID_APP_EXIT zakończyć działanie aplikacji.

   `CWinApp::OnAppExit` obsługuje to polecenie, wysyłając wiadomość WM_CLOSE do głównego okna aplikacji. Standardowe zamykanie aplikacji (monitowanie o zanieczyszczone pliki itd.) jest obsługiwane przez `CFrameWnd` implementację.

   Nie zaleca się dostosowywania tego programu obsługi poleceń. `CWinApp::SaveAllModified`Zalecane jest zastępowanie lub `CFrameWnd` logika zamknięcia.

   W przypadku wybrania opcji wdrożenia tego polecenia zalecamy użycie tego identyfikatora polecenia.

- ID_HELP_INDEX wyświetla listę tematów pomocy z programu. Plik HLP.

    > [!NOTE]
    >  Aby włączyć tę funkcję, należy połączyć ją z `CWinApp` mapą komunikatów klasy pochodnej.

   `CWinApp::OnHelpIndex` obsługuje to polecenie przez niezarządzaną wywoływanie `CWinApp::WinHelp` .

   Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_HELP_USING wyświetla pomoc dotyczącą korzystania z pomocy.

    > [!NOTE]
    >  Aby włączyć tę funkcję, należy połączyć ją z `CWinApp` mapą komunikatów klasy pochodnej.

   `CWinApp::OnHelpUsing` obsługuje to polecenie przez niezarządzaną wywoływanie `CWinApp::WinHelp` .

   Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_CONTEXT_HELP przejściu do trybu pomocy SHIFT-F1.

    > [!NOTE]
    >  Aby włączyć tę funkcję, należy połączyć ją z `CWinApp` mapą komunikatów klasy pochodnej.

   `CWinApp::OnContextHelp` obsługuje to polecenie, ustawiając kursor w trybie pomocy, wprowadzając pętlę modalną i czekając, aż użytkownik wybierze okno, w którym ma zostać uzyskana pomoc. Zapoznaj się z [uwagą techniczną 28](../mfc/tn028-context-sensitive-help-support.md) , aby uzyskać szczegółowe informacje na temat implementacji pomocy MFC.

   Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_HELP zapewnia pomoc dotyczącą bieżącego kontekstu

    > [!NOTE]
    >  Aby włączyć tę funkcję, należy połączyć ją z `CWinApp` mapą komunikatów klasy pochodnej.

   `CWinApp::OnHelp` obsługuje to polecenie, pobierając prawy kontekst pomocy dla kontekstu bieżącego aplikacji. Obsługuje to prostą pomoc dotyczącą klawisza F1, pomoc dotyczącą okien komunikatów i tak dalej. Zapoznaj się z [uwagą techniczną 28](../mfc/tn028-context-sensitive-help-support.md) , aby uzyskać szczegółowe informacje na temat implementacji pomocy MFC.

   Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_DEFAULT_HELP wyświetla domyślną pomoc dla kontekstu

    > [!NOTE]
    >  Aby włączyć tę funkcję, należy połączyć ją z `CWinApp` mapą komunikatów klasy pochodnej.

   To polecenie jest zazwyczaj mapowane na `CWinApp::OnHelpIndex` .

   Można podać inną procedurę obsługi poleceń, jeśli pożądane jest rozróżnienie pomocy domyślnej i indeksu pomocy.

- ID_NEXT_PANE przechodzi do następnego okienka

   `CView` obsługuje to polecenie dla `CSplitterWnd` implementacji. Jeśli widok jest częścią okna rozdzielacza, to polecenie zostanie delegowane do funkcji implementacji `CSplitterWnd::OnNextPaneCmd` . Spowoduje to przeniesienie aktywnego widoku do następnego okienka rozdzielacza.

   To polecenie jest wyłączone, jeśli widok nie znajduje się w rozdzielaczu lub nie ma następnego okienka, do którego chcesz przejść.

   Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_PREV_PANE przechodzi do poprzedniego okienka

   `CView` obsługuje to polecenie dla `CSplitterWnd` implementacji. Jeśli widok jest częścią okna rozdzielacza, to polecenie zostanie delegowane do funkcji implementacji `CSplitterWnd::OnNextPaneCmd` . Spowoduje to przeniesienie aktywnego widoku do poprzedniego okienka rozdzielacza.

   To polecenie jest wyłączone, jeśli widok nie znajduje się w rozdzielaczu lub nie ma poprzedniego okienka, do którego chcesz przejść.

   Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_OLE_INSERT_NEW wstawia nowy obiekt OLE

   Obecnie nie ma standardowej implementacji dla tego polecenia. Musisz zaimplementować tę opcję dla `CView` klasy pochodnej, aby wstawić nowy element OLE/obiekt w bieżącym zaznaczeniu.

   Wszystkie aplikacje klienckie OLE powinny implementować to polecenie. AppWizard z opcją OLE spowoduje utworzenie szkieletowej implementacji `OnInsertObject` w klasie widoku, która będzie musiała zostać ukończona.

   Aby uzyskać pełną implementację tego polecenia, zobacz przykład [OCLIENT](../overview/visual-cpp-samples.md) MFC OLE Sample.

- ID_OLE_EDIT_LINKS edytuje linki OLE

   `COleDocument` obsługuje to polecenie, korzystając z implementacji interfejsu MFC w standardowym oknie dialogowym. Do implementacji tego okna dialogowego można uzyskać dostęp za pomocą `COleLinksDialog` klasy. Jeśli bieżący dokument nie zawiera żadnych linków, polecenie jest wyłączone.

   Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_OLE_VERB_FIRST... Ostatni zakres identyfikatorów dla zleceń OLE

   `COleDocument` używa tego zakresu identyfikatorów poleceń dla zleceń obsługiwanych przez aktualnie zaznaczony element OLE/obiekt. Musi to być zakres, ponieważ dany element OLE/typ obiektu może obsługiwać zero lub więcej czasowników niestandardowych. W menu aplikacji powinien znajdować się jeden element menu o IDENTYFIKATORze ID_OLE_VERB_FIRST. Po uruchomieniu programu menu zostanie zaktualizowane przy użyciu odpowiedniego opisu zlecenia menu (lub menu podręcznego z wieloma zleceniami). Zarządzanie menu OLE jest obsługiwane przez `AfxOleSetEditMenu` , wykonywane w programie obsługi interfejsu wiersza polecenia aktualizacji dla tego polecenia.

   Brak jawnych programów obsługi poleceń do obsługi każdego identyfikatora polecenia w tym zakresie. `COleDocument::OnCmdMsg` został zastąpiony, aby przesłonić wszystkie identyfikatory poleceń z tego zakresu, przekształcić je w liczbę czasowników liczonych od zera i uruchomić serwer dla tego zlecenia (za pomocą polecenia `COleClientItem::DoVerb` ).

   Nie zaleca się dostosowywania ani innego użycia tego zakresu identyfikatora polecenia.

- ID_VIEW_TOOLBAR włącza i wyłącza pasek narzędzi

   `CFrameWnd` obsługuje to polecenie i procedurę obsługi interfejsu wiersza polecenia aktualizacji, aby przełączyć widoczny stan paska narzędzi. Pasek narzędzi musi być oknem podrzędnym ramki z IDENTYFIKATORem okna podrzędnego AFX_IDW_TOOLBAR. Procedura obsługi poleceń faktycznie Przełącza widoczność okna paska narzędzi. `CFrameWnd::RecalcLayout` służy do ponownego rysowania okna ramki z paskiem narzędzi w nowym stanie. Procedura obsługi interfejsu wiersza polecenia aktualizacji sprawdza element menu, gdy pasek narzędzi jest widoczny.

   Nie zaleca się dostosowywania tego programu obsługi poleceń. Jeśli chcesz dodać dodatkowe paski narzędzi, należy sklonować i zmodyfikować procedurę obsługi poleceń oraz procedurę obsługi interfejsu użytkownika aktualizacji poleceń dla tego polecenia.

- ID_VIEW_STATUS_BAR włącza i wyłącza pasek stanu

   To polecenie jest zaimplementowane w `CFrameWnd` taki sam sposób jak ID_VIEW_TOOLBAR, z wyjątkiem tego, że jest używany inny identyfikator okna podrzędnego (AFX_IDW_STATUS_BAR).

## <a name="update-only-command-handlers"></a>Programy obsługi poleceń Update-Only

W paskach stanu są używane różne identyfikatory poleceń standardowych. Używają one tego samego mechanizmu obsługi interfejsu użytkownika polecenia aktualizacji, aby wyświetlić bieżący stan wizualizacji w czasie bezczynności aplikacji. Ponieważ nie mogą zostać wybrane przez użytkownika (oznacza to, że nie można wypchnąć okienka paska stanu), nie ma sensu ON_COMMAND obsługi tych identyfikatorów poleceń.

- ID_INDICATOR_CAPS: wskaźnik blokady zakończenia.

- ID_INDICATOR_NUM: wskaźnik NUM LOCK.

- ID_INDICATOR_SCRL: wskaźnik blokady SCRL.

- ID_INDICATOR_KANA: wskaźnik blokady KANA (dotyczy tylko systemów japońskich).

Wszystkie trzy z nich są zaimplementowane w `CFrameWnd::OnUpdateKeyIndicator` , pomocnika implementacji, który używa identyfikatora polecenia do mapowania odpowiedniego klucza wirtualnego. Typowa implementacja włącza lub wyłącza (w przypadku okienka stanu wyłączone = Brak tekstu) obiekt w zależności od tego, `CCmdUI` czy odpowiedni klucz wirtualny jest aktualnie zablokowany.

Nie zaleca się dostosowywania tego programu obsługi poleceń.

- ID_INDICATOR_EXT: rozszerzony wskaźnik SELECT.

- ID_INDICATOR_OVR: wskaźnik przekreślania.

- ID_INDICATOR_REC: wskaźnik rejestrowania.

Obecnie nie ma standardowej implementacji dla tych wskaźników.

Jeśli zdecydujesz się zaimplementować te wskaźniki, zalecamy używanie tych identyfikatorów wskaźnika i utrzymywanie uporządkowania wskaźników na pasku stanu (czyli w następującej kolejności: EXT, CAP, NUM, SCRL, OVR, REC).

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
