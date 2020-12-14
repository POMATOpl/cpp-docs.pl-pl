---
description: 'Dowiedz się więcej o: Instrukcje: Dodawanie routingu poleceń do kontrolki Windows Forms'
title: 'Porady: dodawanie routingu poleceń do formantu interfejsu Windows Forms'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
ms.openlocfilehash: b46087d7df3da5f402432731db4b994b257a385b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335421"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>Porady: dodawanie routingu poleceń do formantu interfejsu Windows Forms

[CWinFormsView](../mfc/reference/cwinformsview-class.md) kieruje polecenia i komunikaty polecenia interfejsu użytkownika do kontrolki użytkownika, aby zezwolić na obsługę poleceń MFC (na przykład elementów menu ramek i przycisków paska narzędzi).

Kontrolka użytkownika używa [ICommandTarget:: Initialize](../mfc/reference/icommandtarget-interface.md#initialize) do przechowywania odwołania do obiektu źródłowego polecenia w `m_CmdSrc` , jak pokazano w poniższym przykładzie. Aby użyć należy `ICommandTarget` dodać odwołanie do mfcmifc80.dll.

`CWinFormsView` obsługuje kilka typowych powiadomień w widoku MFC, przekazując je do zarządzanej kontrolki użytkownika. Te powiadomienia obejmują metody [OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate), [OnUpdate](../mfc/reference/iview-interface.md#onupdate) i [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) .

W tym temacie założono, że wcześniej zostały wykonane [następujące instrukcje: Tworzenie kontrolki użytkownika i hosta w oknie dialogowym](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) i [instrukcje: Tworzenie formantu użytkownika i widoku MDI hosta](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

### <a name="to-create-the-mfc-host-application"></a>Aby utworzyć aplikację hosta MFC

1. Otwórz bibliotekę formantów Windows Forms utworzoną w [instrukcje: Tworzenie kontrolki użytkownika i hosta w oknie dialogowym](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).

1. Dodaj odwołanie do mfcmifc80.dll, które można wykonać, klikając prawym przyciskiem myszy węzeł projektu w **Eksplorator rozwiązań**, wybierając pozycję **Dodaj**, **odwołanie**, a następnie przechodząc do pozycji Microsoft Visual Studio 10.0 \ VC\atlmfc\lib.

1. Otwórz UserControl1.Designer.cs i Dodaj następującą instrukcję using:

    ```
    using Microsoft.VisualC.MFC;
    ```

1. Ponadto w UserControl1.Designer.cs Zmień ten wiersz:

    ```
    partial class UserControl1
    ```

   wprowadź następujące zmiany:

    ```
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget
    ```

1. Dodaj jako pierwszy wiersz definicji klasy dla `UserControl1` :

    ```
    private ICommandSource m_CmdSrc;
    ```

1. Dodaj następujące definicje metod do `UserControl1` (w następnym kroku utworzymy identyfikator kontrolki MFC):

    ```
    public void Initialize (ICommandSource cmdSrc)
    {
       m_CmdSrc = cmdSrc;
       // need ID of control in MFC dialog and callback function
       m_CmdSrc.AddCommandHandler(32771, new CommandHandler (singleMenuHandler));
    }

    private void singleMenuHandler (uint cmdUI)
    {
       // User command handler code
       System.Windows.Forms.MessageBox.Show("Custom menu option was clicked.");
    }
    ```

1. Otwórz aplikację MFC utworzoną w temacie [How to: Create the user Control and Host MDI View](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

1. Dodaj opcję menu, która zostanie wywołana `singleMenuHandler` .

   Przejdź do **Widok zasobów** (Ctrl + Shift + E), rozwiń folder **menu** , a następnie kliknij dwukrotnie pozycję **IDR_MFC02TYPE**. Spowoduje to wyświetlenie edytora menu.

   Dodaj opcję menu u dołu menu **Widok** . Zwróć uwagę na identyfikator opcji menu w oknie **Właściwości** . Zapisz plik.

   W **Eksplorator rozwiązań** Otwórz plik Resource. h, skopiuj wartość identyfikatora dla właśnie dodanej opcji menu i wklej tę wartość jako pierwszy parametr `m_CmdSrc.AddCommandHandler` wywołania w `Initialize` metodzie projektu C# (zastępowanie w `32771` razie potrzeby).

1. Skompiluj i Uruchom projekt.

   W menu **Kompilacja** kliknij pozycję **Kompiluj rozwiązanie**.

   W menu **debugowanie** kliknij polecenie **Uruchom bez debugowania**.

   Wybierz dodaną opcję menu. Zauważ, że metoda w pliku. dll jest wywoływana.

## <a name="see-also"></a>Zobacz też

[Hostowanie formantu użytkownika interfejsu Windows Forms jako widoku MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[ICommandSource, interfejs](../mfc/reference/icommandsource-interface.md)<br/>
[ICommandTarget, interfejs](../mfc/reference/icommandtarget-interface.md)
