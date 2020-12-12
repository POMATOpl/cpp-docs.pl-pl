---
description: 'Dowiedz się więcej o: TN026: DDX i DDV procedur'
title: 'TN026: procedury DDX i DDV'
ms.date: 06/28/2018
f1_keywords:
- DDX
- DDV
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
ms.openlocfilehash: 1e5c8d3679b7e91ad7f356c1e6f6badc61cdd46f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215706"
---
# <a name="tn026-ddx-and-ddv-routines"></a>TN026: procedury DDX i DDV

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

W tej uwadze opisano architekturę wymiany danych (DDX) i sprawdzanie poprawności danych (DDV). Opisano w nim również sposób pisania procedury DDX_ lub DDV_ oraz sposobu, w jaki można zwiększyć ClassWizard do korzystania z własnych procedur.

## <a name="overview-of-dialog-data-exchange"></a>Omówienie wymiany danych w oknie dialogowym

Wszystkie funkcje danych okna dialogowego są wykonywane przy użyciu kodu języka C++. Nie ma specjalnych zasobów ani magicznych makr. Sercem mechanizmu jest funkcja wirtualna, która została zastąpiona w każdej klasie okna dialogowego, która umożliwia wymianę i weryfikację danych w oknie dialogowym. Jest on zawsze znaleziony w tej postaci:

```cpp
void CMyDialog::DoDataExchange(CDataExchange* pDX)
{
    CDialog::DoDataExchange(pDX);   // call base class

    //{{AFX_DATA_MAP(CMyDialog)
        <data_exchange_function_call>
        <data_validation_function_call>
    //}}AFX_DATA_MAP
}
```

Specjalny format AFX komentarzy umożliwia ClassWizard do lokalizowania i edytowania kodu w ramach tej funkcji. Kod niezgodny z ClassWizard powinien być umieszczony poza specjalnymi komentarzami formatu.

W powyższym przykładzie \<data_exchange_function_call> ma postać:

```cpp
DDX_Custom(pDX, nIDC, field);
```

i \<data_validation_function_call> jest opcjonalne i ma postać:

```cpp
DDV_Custom(pDX, field, ...);
```

W każdej funkcji może być dołączona więcej niż jedna para DDX_/DDV_ `DoDataExchange` .

Zobacz "afxdd_. h", aby wyświetlić listę wszystkich procedur wymiany danych okna dialogowego i procedur sprawdzania poprawności danych okna dialogowego dostarczonych z MFC.

Dane okna dialogowego są tylko następujące: dane elementów członkowskich w `CMyDialog` klasie. Nie jest on przechowywany w strukturze ani niczego podobne.

## <a name="notes"></a>Uwagi

Chociaż nazywamy to "dane okna dialogowego", wszystkie funkcje są dostępne w każdej klasie pochodnej od `CWnd` i nie są ograniczone do tylko okien dialogowych.

Początkowe wartości danych są ustawiane w standardowym konstruktorze języka C++, zazwyczaj w bloku z `//{{AFX_DATA_INIT` i `//}}AFX_DATA_INIT` komentarzami.

`CWnd::UpdateData` jest operacją, która wykonuje inicjalizację i obsługę błędów wokół wywołania `DoDataExchange` .

`CWnd::UpdateData`W dowolnym momencie możesz wywoływać, aby przeprowadzić wymianę danych i weryfikację. Domyślnie `UpdateData` (true) jest wywoływana w domyślnej `CDialog::OnOK` obsłudze i `UpdateData` (false) jest wywoływana domyślnie `CDialog::OnInitDialog` .

Procedura DDV_ powinna natychmiast przestrzegać procedury DDX_ dla tego *pola*.

## <a name="how-does-it-work"></a>Jak to działa

Nie trzeba zrozumieć następujących informacji, aby użyć danych okna dialogowego. Jednak zrozumienie, jak to działa w tle, pomoże Ci napisać własną procedurę wymiany lub walidacji.

`DoDataExchange`Funkcja członkowska jest podobnie jak `Serialize` funkcja członkowska — jest odpowiedzialna za pobieranie lub ustawianie danych do/z formularza zewnętrznego (w tym przypadku kontrolek w oknie dialogowym) z/do danych elementu członkowskiego w klasie. Parametr *PDX* jest kontekstem do wykonywania wymiany danych i jest podobny do `CArchive` parametru `CObject::Serialize` . *PDX* ( `CDataExchange` obiekt) ma flagę kierunku, podobnie jak `CArchive` ma flagę kierunku:

- Jeśli `!m_bSaveAndValidate` następnie załaduj stan danych do kontrolek.

- W przypadku `m_bSaveAndValidate` Ustawienia stanu danych z kontrolek.

Walidacja występuje tylko wtedy, gdy `m_bSaveAndValidate` jest ustawiona. Wartość `m_bSaveAndValidate` jest określana przez parametr bool do `CWnd::UpdateData` .

Istnieją trzy inne interesujące `CDataExchange` elementy członkowskie:

- `m_pDlgWnd`: Okno (zazwyczaj okno dialogowe), które zawiera kontrolki. Ma to na celu uniemożliwienie wywoływania DDX_ i DDV_ funkcji globalnych przed przekazaniem elementu "This" do każdej procedury DDX/DDV.

- `PrepareCtrl`i `PrepareEditCtrl` : przygotowuje kontrolkę okna dialogowego do wymiany danych. Przechowuje dojście kontrolki do ustawiania fokusu, jeśli sprawdzanie poprawności zakończy się niepowodzeniem. `PrepareCtrl` jest używany dla kontrolek, które nie `PrepareEditCtrl` są edytowane i są używane do edycji kontrolek.

- `Fail`: Wywołuje się po utworzeniu okna komunikatu z alertem użytkownika o błędzie wejściowym. Ta procedura spowoduje przywrócenie fokusu do ostatniej kontrolki (ostatnie wywołanie do `PrepareCtrl` lub `PrepareEditCtrl` ) i zgłoszenie wyjątku. Ta funkcja członkowska może być wywoływana z poziomu procedur DDX_ i DDV_.

## <a name="user-extensions"></a>Rozszerzenia użytkownika

Istnieje kilka sposobów, aby zwiększyć domyślny mechanizm DDX/DDV. Można:

- Dodaj nowe typy danych.

    ```cpp
    CTime
    ```

- Dodaj nowe procedury wymiany (DDX_).

    ```cpp
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);
    ```

- Dodaj nowe procedury walidacji (DDV_).

    ```cpp
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);
    // make sure time is in the future or past
    ```

- Przekaż dowolne wyrażenia do procedur walidacji.

    ```cpp
    DDV_MinMax(pDX, age, 0, m_maxAge);
    ```

    > [!NOTE]
    > Takie dowolne wyrażenia nie mogą być edytowane przez ClassWizard i dlatego powinny być przenoszone poza specjalne Komentarze do formatu (//{{AFX_DATA_MAP (CMyClass)).

`DoDialogExchange`Funkcja członkowska zawiera warunkowe lub inne prawidłowe instrukcje języka C++ z wywołaniami funkcji wzajemnego wymiany i walidacji.

```cpp
//{{AFX_DATA_MAP(CMyClass)
DDX_Check(pDX, IDC_SEX, m_bFemale);
DDX_Text(pDX, IDC_EDIT1, m_age);
//}}AFX_DATA_MAP
if (m_bFemale)
    DDV_MinMax(pDX, age, 0, m_maxFemaleAge);
else
    DDV_MinMax(pDX, age, 0, m_maxMaleAge);
```

> [!NOTE]
> Jak pokazano powyżej, taki kod nie może być edytowany przez ClassWizard i powinien być używany tylko poza komentarzem w formacie specjalnym.

## <a name="classwizard-support"></a>Obsługa ClassWizard

ClassWizard obsługuje podzbiór dostosowań DDX/DDV, umożliwiając integrację własnych DDX_ i DDV_ procedur z interfejsem użytkownika ClassWizard. Jest to przydatne tylko wtedy, gdy planujesz ponownie wykorzystać określone procedury DDX i DDV w projekcie lub w wielu projektach.

W tym celu specjalne wpisy są wprowadzane w DDX. CLW (poprzednie wersje Visual C++ przechowywane te informacje w APSTUDIO.INI) lub w projekcie. Plik CLW. Wpisy specjalne można wprowadzać w sekcji [ogólne informacje] projektu. Plik CLW lub w sekcji [ExtraDDX] pliku DDX. CLW w katalogu \Program Files\Microsoft Visual Studio\Visual C++ \Bin. Może być konieczne utworzenie pliku DDX. CLW, jeśli jeszcze nie istnieje. Jeśli planujesz używać niestandardowych procedur DDX_/DDV_ tylko w określonym projekcie, Dodaj wpisy do sekcji [ogólne informacje] w projekcie. Zamiast tego należy użyć pliku CLW. Jeśli planujesz używać procedur w wielu projektach, Dodaj wpisy do sekcji [ExtraDDX] w DDX. CLW.

Ogólny format tych specjalnych wpisów to:

> ExtraDDXCount =*n*

gdzie *n* jest liczbą ExtraDDX? wiersze do wykonania w formularzu

> ExtraDDX? =*klucze*; *Visual-Keys*; *Monituj*; *Typ*; *initValue*; *DDX_Proc* [; *DDV_Proc*; *prompt1*; *arg1* [; *prompt2*; *fmt2*]]

miejscu? jest liczbą 1- *n* wskazującą, który typ DDX należy do definiowanej listy.

Każde pole jest rozdzielane znakiem ";". Pola i ich cele są opisane poniżej.

- *ponownie*

  Lista pojedynczych znaków wskazujących, że dla tego typu okna dialogowego jest dozwolony ten typ zmiennej.

  |Znak|Dozwolona kontrola|
  |-|-|
  E | edytuj
  C | pole wyboru dwóch Stanów
  c | pole wyboru Tri-State
  R | pierwszy przycisk radiowy w grupie
  L | niesortowane pole listy
  l | posortowane pole listy
  M | pole kombi (z edycji elementu)
  N | Lista rozwijana niesortowana
  n | posortowana lista rozwijana
  1 | Jeśli Wstaw DDX należy dodać do nagłówka listy (domyślnie jest to dodanie do ogona), jest on zazwyczaj używany dla procedur DDX, które przesyłają Właściwość "Control".

- *VB — klucze*

  To pole jest używane tylko w 16-bitowym produkcie dla formantów VBX (VBX formanty nie są obsługiwane w produkcie 32-bitowym).

- *pytać*

  Ciąg do umieszczenia w polu kombi właściwości (brak cudzysłowów)

- *Wprowadź*

  Pojedynczy identyfikator dla typu do emisji w pliku nagłówkowym. W naszym przykładzie powyżej z DDX_Time będzie to miało wartość CTime.

- *VB — klucze*

  Nieużywane w tej wersji i powinny być zawsze puste

- *initValue*

  Wartość początkowa — 0 lub puste. Jeśli to pole jest puste, w sekcji//{AFX_DATA_INIT pliku implementacji nie zostanie zapisany żaden wiersz inicjalizacji. Dla obiektów języka C++ (takich jak `CString` , itd `CTime` .), które mają konstruktory gwarantujące poprawną inicjalizację, należy używać pustego wpisu.

- *DDX_Proc*

  Pojedynczy identyfikator procedury DDX_ej. Nazwa funkcji języka C++ musi rozpoczynać się od "DDX_", ale nie zawiera "DDX_" w \<DDX_Proc> identyfikatorze. W powyższym przykładzie \<DDX_Proc> identyfikatorem będzie czas. Gdy ClassWizard zapisuje wywołanie funkcji do pliku implementacji w sekcji {{AFX_DATA_MAP, dołącza tę nazwę do DDX_, w ten sposób dociera do DDX_Time.

- *komentować*

  Komentarz do wyświetlania w oknie dialogowym dla zmiennej o tym DDX. Umieść dowolny tekst w tym miejscu i zwykle Podaj coś, który opisuje operację wykonywaną przez parę DDX/DDV.

- *DDV_Proc*

  Część DDV wpisu jest opcjonalna. Nie wszystkie procedury DDX mają odpowiednie procedury DDV. Często wygodniejszym rozwiązaniem jest dołączenie fazy weryfikacji jako integralnej części transferu. Jest to często przypadek, gdy procedura DDV nie wymaga żadnych parametrów, ponieważ ClassWizard nie obsługuje procedur DDV bez żadnych parametrów.

- *ARG*

  Pojedynczy identyfikator procedury DDV_ej. Nazwa funkcji języka C++ musi rozpoczynać się od "DDV_", ale nie zawiera "DDX_" w \<DDX_Proc> identyfikatorze.

  po *ARG* następuje 1 lub 2 DDV argumentów:

  - *promptN*

      Ciąg, który ma zostać umieszczony powyżej elementu edycji (z & dla akceleratora).

  - *fmtN*

      Formatuj znak dla typu ARG, jeden z:

      |Znak|Typ|
      |-|-|
      |d | int|
      |u | unsigned int|
      |D | long int (Long)|
      |U | Long unsigned (is, DWORD)|
      |f | float|
      |F | double|
      |s | ciąg|

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
