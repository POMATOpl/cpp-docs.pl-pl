---
description: 'Dowiedz się więcej o: hosting kontrolki użytkownika formularza systemu Windows w oknie dialogowym MFC'
title: Hostowanie kontrolki użytkownika formularza systemu Windows w oknie dialogowym MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 3ccfbb32132f5732c244473c652bb6b2df175efa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335447"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>Hostowanie kontrolki użytkownika formularza systemu Windows w oknie dialogowym MFC

MFC obsługuje kontrolkę Windows Forms jako specjalny rodzaj kontrolki ActiveX i komunikuje się z formantem przy użyciu interfejsów ActiveX oraz właściwości i metod <xref:System.Windows.Forms.Control> klasy. Zalecamy używanie .NET Framework właściwości i metod do działania na formancie.

Aby uzyskać przykładową aplikację, która zawiera Windows Forms używane z MFC, zobacz [integrację MFC i Windows Forms](https://www.microsoft.com/download/details.aspx?id=2113).

> [!NOTE]
> W bieżącej wersji `CDialogBar` obiekt nie może hostować Windows Forms formantów.

## <a name="in-this-section"></a>W tej sekcji

[Instrukcje: Tworzenie kontrolki użytkownika i hosta w oknie dialogowym](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[Instrukcje: wykonywanie powiązania danych DDX/DDV za pomocą Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[Instrukcje: ujścia zdarzeń Windows Forms z natywnych klas języka C++](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>Dokumentacja

Klasa [CWinFormsControl](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog](../mfc/reference/cdialog-class.md) Class &#124; [CWnd](../mfc/reference/cwnd-class.md) &#124;<xref:System.Windows.Forms.Control>

## <a name="see-also"></a>Zobacz też

[Korzystanie z kontrolki użytkownika formularza systemu Windows w MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Różnice w programowaniu Windows Forms/MFC](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[Hostowanie formantu użytkownika interfejsu Windows Forms jako widoku MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[Hostowanie kontrolki użytkownika formularza systemu Windows jako okna dialogowego MFC](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
