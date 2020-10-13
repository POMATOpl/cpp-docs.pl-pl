---
title: 'Instrukcje: Powiązanie danych DDX-DDV za pomocą interfejsu Windows Forms'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
ms.openlocfilehash: a0759eba1c55e72f2c0a99964b0b2d254df82a25
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008321"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>Porady: powiązanie danych DDX/DDV za pomocą interfejsu Windows Forms

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) wywołuje [CWinFormsControl:: CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) , aby utworzyć KONTROLkę odpowiadającą identyfikatorowi kontroli zasobów. Jeśli używasz `DDX_ManagedControl` do `CWinFormsControl` kontrolki (w kodzie wygenerowanym przez kreatora), nie należy wywoływać `CreateManagedControl` jawnie dla tej samej kontrolki.

Wywołanie `DDX_ManagedControl` w [CWnd::D odataexchange](../mfc/reference/cwnd-class.md#dodataexchange) , aby utworzyć kontrolki z identyfikatorów zasobów. W przypadku wymiany danych nie trzeba używać funkcji DDX/DDV z kontrolkami Windows Forms. Zamiast tego można umieścić kod w celu uzyskania dostępu do właściwości kontrolki zarządzanej w `DoDataExchange` metodzie klasy okna dialogowego (lub widoku), jak w poniższym przykładzie.

Poniższy przykład pokazuje, jak powiązać natywny ciąg języka C++ z kontrolką użytkownika platformy .NET.

## <a name="example-ddxddv-data-binding"></a>Przykład: DDX/DDV powiązanie danych

Poniżej znajduje się przykład powiązania danych DDX/DDV ciągu MFC `m_str` ze zdefiniowaną przez użytkownika `NameText` właściwością kontrolki użytkownika platformy .NET.

Kontrolka jest tworzona, gdy [CDialog:: OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) wywołuje po `CMyDlg::DoDataExchange` raz pierwszy, więc każdy kod, który odwołuje się, `m_UserControl` musi występować po `DDX_ManagedControl` wywołaniu.

Możesz zaimplementować ten kod w aplikacji MFC01 utworzonej w [instrukcje: Tworzenie kontrolki użytkownika i hosta w oknie dialogowym](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).

Umieść następujący kod w deklaracji CMFC01Dlg:

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example-implement-dodataexchange"></a>Przykład: Implementuj DoDataExchange ()

Umieść następujący kod w implementacji CMFC01Dlg:

```cpp
void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
{
   CDialog::DoDataExchange(pDX);
   DDX_ManagedControl(pDX, IDC_CTRL1, m_MyControl);

   if (pDX->m_bSaveAndValidate) {
      m_str = m_MyControl->textBox1->Text;
   } else
   {
      m_MyControl->textBox1->Text = gcnew System::String(m_str);
   }
}
```

## <a name="example-add-handler-method"></a>Przykład: Dodaj metodę procedury obsługi

Teraz dodamy metodę obsługi dla kliknięcia przycisku OK. Kliknij kartę **Widok zasobów** . W Widok zasobów kliknij dwukrotnie pozycję włączone `IDD_MFC01_DIALOG` . Zasób okna dialogowego pojawia się w edytorze zasobów. Następnie kliknij dwukrotnie przycisk OK.

Zdefiniuj program obsługi w następujący sposób.

```cpp
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example-set-the-textbox-text"></a>Przykład: Ustaw tekst textBox

Dodaj następujący wiersz do implementacji BOOL CMFC01Dlg:: OnInitDialog ().

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

Teraz możesz skompilować i uruchomić aplikację. Zauważ, że dowolny tekst w polu tekstowym będzie wyświetlany w oknie komunikatu podręcznego po zamknięciu aplikacji.

## <a name="see-also"></a>Zobacz też

[Klasa CWinFormsControl](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::D oDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)
