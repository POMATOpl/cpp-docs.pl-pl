---
description: 'Dowiedz się więcej na temat: Instrukcje: wywoływanie właściwości i metod kontrolki Windows Forms'
title: 'Porady: wywoływanie właściwości i metod formantu interfejsu Windows Forms'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- method calls, Windows Forms
- calling methods, Windows Forms control
- calling properties, Windows Forms control
- Windows Forms controls [C++], methods
- calling properties
- Windows Forms controls [C++], properties
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
ms.openlocfilehash: a797084a28eefec27699814a09c8521da7460bc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268408"
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>Porady: wywoływanie właściwości i metod formantu interfejsu Windows Forms

Ponieważ [CWinFormsView:: GetControl](../mfc/reference/cwinformsview-class.md#getcontrol) zwraca wskaźnik do <xref:System.Windows.Forms.Control?displayProperty=fullName> , a nie wskaźnik do, zaleca się `WindowsControlLibrary1::UserControl1` dodanie elementu członkowskiego typu formantu użytkownika i zainicjowanie go w [widoku IView:: OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate). Teraz możesz wywoływać metody i właściwości przy użyciu polecenia `m_ViewControl` .

W tym temacie założono, że wcześniej zostały wykonane [następujące instrukcje: Tworzenie kontrolki użytkownika i hosta w oknie dialogowym](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) i [instrukcje: Tworzenie formantu użytkownika i widoku MDI hosta](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

### <a name="to-create-the-mfc-host-application"></a>Aby utworzyć aplikację hosta MFC

1. Otwórz aplikację MFC utworzoną w temacie [How to: Create the user Control and Host MDI View](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

1. Dodaj następujący wiersz do sekcji przesłania publiczne `CMFC02View` deklaracji klasy w MFC02View. h.

   `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`

1. Dodaj zastąpienie dla OnInitialupdate.

   Wyświetlanie okna **Właściwości** (F4). W **Widok klasy** (Ctrl + Shift + C) wybierz pozycję Klasa CMFC02View. W oknie **Właściwości** wybierz ikonę zastąpień. Scoll listę do OnInitialUpdate. Kliknij listę rozwijaną i wybierz pozycję \<Add> . W MFC02View. cpp. Upewnij się, że treść funkcji OnInitialUpdate jest następująca:

    ```
    CWinFormsView::OnInitialUpdate();
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());
    m_ViewControl->textBox1->Text = gcnew System::String("hi");
    ```

1. Skompiluj i Uruchom projekt.

   W menu **Kompilacja** kliknij pozycję **Kompiluj rozwiązanie**.

   W menu **debugowanie** kliknij polecenie **Uruchom bez debugowania**.

   Zauważ, że pole tekstowe jest teraz zainicjowane.

## <a name="see-also"></a>Zobacz też

[Hostowanie formantu użytkownika interfejsu Windows Forms jako widoku MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
