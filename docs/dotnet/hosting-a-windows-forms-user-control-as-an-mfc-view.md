---
description: Dowiedz się więcej o tym, jak hostować Windows Forms kontrolkę użytkownika jako widok MFC
title: Hostowanie formantu użytkownika interfejsu Windows Forms jako widoku MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
ms.openlocfilehash: 4e66d4ace83e0026ec7a95cbe1b94462a163dddf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164643"
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>Hostowanie formantu użytkownika interfejsu Windows Forms jako widoku MFC

MFC używa klasy CWinFormsView do hostowania kontrolki użytkownika Windows Forms w widoku MFC. Widoki Windows Forms MFC są kontrolkami ActiveX. Kontrolka użytkownika jest hostowana jako element podrzędny widoku natywnego i zajmuje cały obszar klienta widoku natywnego.

Wynik końcowy przypomina model używany przez [klasę CFormView](../mfc/reference/cformview-class.md). Dzięki temu można korzystać z projektanta Windows Forms i środowiska uruchomieniowego w celu tworzenia zaawansowanych widoków opartych na formularzach.

Ponieważ widoki Windows Forms MFC są kontrolkami ActiveX, nie są one takie same `hwnd` jak widoki MFC. Nie można ich również przekazywać jako wskaźnika do widoku [CView](../mfc/reference/cview-class.md) . Ogólnie rzecz biorąc, użyj .NET Framework metod do pracy z widokami Windows Forms i zależą od systemu Win32.

Aby uzyskać przykładową aplikację, która zawiera Windows Forms używane z MFC, zobacz [integrację MFC i Windows Forms](https://www.microsoft.com/download/details.aspx?id=2113).

## <a name="in-this-section"></a>W tej sekcji

[Instrukcje: Tworzenie kontrolki użytkownika i hostowanie widoku MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

[Instrukcje: Dodawanie routingu poleceń do kontrolki Windows Forms](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

[Instrukcje: wywoływanie właściwości i metod kontrolki Windows Forms](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)

## <a name="see-also"></a>Zobacz też

[Korzystanie z kontrolki użytkownika formularza systemu Windows w MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Instrukcje: autoryzowanie kontrolek złożonych](/dotnet/framework/winforms/controls/how-to-author-composite-controls)
