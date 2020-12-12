---
description: 'Dowiedz się więcej na temat: jak utworzyć kontrolkę użytkownika i hosta w oknie dialogowym'
title: 'Porady: tworzenie kontrolki użytkownika i hosta w oknie dialogowym'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
ms.openlocfilehash: 400906344f47f7100e52319adb37c39d1fb370e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283968"
---
# <a name="how-to-create-the-user-control-and-host-in-a-dialog-box"></a>Porady: tworzenie kontrolki użytkownika i hosta w oknie dialogowym

W krokach w tym artykule założono, że tworzysz projekt oparty na oknach dialogowych ([CDialog Class](../mfc/reference/cdialog-class.md)) Microsoft Foundation CLASSES (MFC), ale możesz również dodać obsługę kontrolki Windows Forms do istniejącego okna dialogowego MFC.

### <a name="to-create-the-net-user-control"></a>Aby utworzyć kontrolkę użytkownika platformy .NET

1. Utwórz projekt biblioteki formantów Windows Forms Visual C# o nazwie `WindowsFormsControlLibrary1` .

   W menu **plik** kliknij pozycję **Nowy** , a następnie kliknij pozycję **projekt**. W folderze **Visual C#** wybierz pozycję **Biblioteka formantów Windows Forms**.

   Zaakceptuj `WindowsFormsControlLibrary1` nazwę projektu, klikając przycisk **OK**.

   Domyślnie nazwą formantu .NET będzie `UserControl1` .

1. Dodaj kontrolki podrzędne do `UserControl1` .

   W **przyborniku** Otwórz listę **wszystkie Windows Forms** . Przeciągnij kontrolkę **Button** na `UserControl1` powierzchnię projektu.

   Dodaj również kontrolkę **TextBox** .

1. W **Eksplorator rozwiązań** kliknij dwukrotnie pozycję **UserControl1.Designer.cs** , aby otworzyć ją do edycji. Zmień deklaracje pola tekstowego i przycisk z `private` na `public` .

1. Skompiluj projekt.

   W menu **Kompilacja** kliknij pozycję **Kompiluj rozwiązanie**.

### <a name="to-create-the-mfc-host-application"></a>Aby utworzyć aplikację hosta MFC

1. Utwórz projekt aplikacji MFC.

   W menu **plik** kliknij pozycję **Nowy** , a następnie kliknij pozycję **projekt**. W folderze **Visual C++** wybierz pozycję **aplikacja MFC**.

   W polu **Nazwa** wpisz `MFC01`. Zmień ustawienie rozwiązania na **Dodaj do rozwiązania**. Kliknij przycisk **OK**.

   W **Kreatorze aplikacji MFC** w obszarze Typ aplikacji wybierz pozycję **okno dialogowe**. Zaakceptuj pozostałe ustawienia domyślne i kliknij przycisk **Zakończ**. Spowoduje to utworzenie aplikacji MFC, która ma okno dialogowe MFC.

1. Dodaj kontrolkę symbol zastępczy do okna dialogowego MFC.

   W menu **Widok** kliknij **Widok zasobów**. W **Widok zasobów** rozwiń folder **okna dialogowego** i kliknij dwukrotnie `IDD_MFC01_DIALOG` . Zasób okna dialogowego pojawia się w **edytorze zasobów**.

   W **przyborniku** Otwórz listę **Edytor okien dialogowych** . Przeciągnij **statyczny formant tekstowy** do zasobu okna dialogowego. Formant **tekstu statycznego** będzie używany jako symbol zastępczy dla kontrolki Windows Forms .NET. Zmień rozmiar na rozmiar w przybliżeniu Windows Forms formantu.

   W oknie **Właściwości** Zmień **Identyfikator** kontrolki **tekst statyczny** na `IDC_CTRL1` **wartość PRAWDA**. 

1. Skonfiguruj projekt dla obsługi środowiska uruchomieniowego języka wspólnego (CLR).

   W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy węzeł projektu MFC01, a następnie kliknij polecenie **Właściwości**.

   W oknie dialogowym **strony właściwości** w obszarze **Właściwości konfiguracji** wybierz pozycję **Ogólne**. W sekcji **wartości domyślne projektu** Ustaw **obsługę środowiska uruchomieniowego** CLR na **obsługę środowiska uruchomieniowego CLR (/CLR)**.

   W obszarze **Właściwości konfiguracji** rozwiń węzeł **C/C++** i wybierz węzeł **Ogólne** . Ustaw **Format informacji debugowania** dla **bazy danych programu (/ZI)**.

   Wybierz węzeł **generowanie kodu** . Ustaw **opcję Włącz minimalną** ponowną kompilację na wartość **no (/GM-)**. Ustaw również **podstawowe testy środowiska uruchomieniowego** na **domyślne**.

   Kliknij przycisk **OK**, aby zastosować zmiany.

1. Dodaj odwołanie do kontrolki .NET.

   W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy węzeł projektu MFC01, a następnie kliknij polecenie **Dodaj**, **odwołania**. Na **stronie właściwości** kliknij pozycję **Dodaj nowe odwołanie**, wybierz pozycję **WindowsFormsControlLibrary1** (na karcie **projekty** ), a następnie kliknij przycisk **OK**. Spowoduje to dodanie odwołania w postaci opcji kompilatora [/Fu](../build/reference/fu-name-forced-hash-using-file.md) , tak aby program skompiluje. Umieszcza również kopię WindowsFormsControlLibrary1.dll w folderze projektu \MFC01\, dzięki czemu program zostanie uruchomiony.

1. W stdafx. h Znajdź ten wiersz:

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   W tym celu Dodaj następujące wiersze:

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. Dodaj kod, aby utworzyć zarządzany formant.

   Najpierw Zadeklaruj zarządzany formant. W pliku mfc01dlg. h przejdź do deklaracji klasy okna dialogowego i Dodaj element członkowski danych dla kontrolki użytkownika w zakresie chronionym w następujący sposób.

    ```
    class CMFC01Dlg : public CDialog
    {
       // ...
       // Data member for the .NET User Control:
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;
    ```

   Następnie podaj implementację zarządzanego formantu. W pliku mfc01dlg. cpp w oknie dialogowym przesłonięcie, `CMFC01Dlg::DoDataExchange` które zostało wygenerowane przez Kreatora aplikacji MFC (nie `CAboutDlg::DoDataExchange` , który znajduje się w tym samym pliku), Dodaj następujący kod, aby utworzyć zarządzany formant i skojarzyć go z symbolem zastępczym miejsca statycznego IDC_CTRL1.

    ```
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
    {
       CDialog::DoDataExchange(pDX);
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);
    }
    ```

1. Skompiluj i Uruchom projekt.

   W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy pozycję **MFC01** , a następnie kliknij pozycję **Ustaw jako projekt startowy**.

   W menu **Kompilacja** kliknij pozycję **Kompiluj rozwiązanie**.

   W menu **debugowanie** kliknij polecenie **Uruchom bez debugowania**. W oknie dialogowym MFC powinna zostać wyświetlona kontrolka Windows Forms.

## <a name="see-also"></a>Zobacz też

[Hostowanie kontrolki użytkownika formularza systemu Windows w oknie dialogowym MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)
