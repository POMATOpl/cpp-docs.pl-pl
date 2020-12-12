---
description: 'Dowiedz się więcej na temat: korzystanie z kontrolki użytkownika formularza systemu Windows w MFC'
title: Używanie formantu użytkownika formularza systemu Windows w MFC
ms.date: 01/08/2018
helpviewer_keywords:
- MFC [C++], Windows Forms support
- interoperability [C++], Windows Forms in MFC
- interoperability [C++], MFC
- interop [C++], Windows Forms in MFC
- interop [C++], MFC
- Windows Forms [C++], MFC support
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
ms.openlocfilehash: 61022d241faba1650d1a044ef6d3667febe34cde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319030"
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>Używanie formantu użytkownika formularza systemu Windows w MFC

Przy użyciu klas obsługi MFC Windows Forms można hostować Windows Forms formantów w aplikacjach MFC jako kontrolki ActiveX w oknach dialogowych MFC lub w widokach. Ponadto formularze Windows Forms mogą być hostowane jako okna dialogowe MFC.

W poniższych sekcjach opisano, jak:

- Hostowanie kontrolki Windows Forms w oknie dialogowym MFC.

- Hostowanie kontrolki użytkownika Windows Forms jako widoku MFC.

- Hostowanie Windows Forms formularza jako okna dialogowego MFC.

> [!NOTE]
> Integracja MFC Windows Forms działa tylko w projektach, które łączą się dynamicznie z MFC (w których `_AFXDLL` zdefiniowane są projekty).

> [!NOTE]
> Podczas kompilowania aplikacji przy użyciu prywatnej (zmodyfikowanej) kopii biblioteki DLL interfejsów Windows Forms MFC (mfcmifc80.dll) instalacja nie powiedzie się w pamięci podręcznej, o ile nie zastąpisz klucza firmy Microsoft własnym kluczem dostawcy. Aby uzyskać więcej informacji na temat podpisywania zestawu, zobacz [programowanie z](/dotnet/framework/app-domains/programming-with-assemblies) zestawami i [zestawy o silnych nazwach (podpisywanie zestawów) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

Jeśli aplikacja MFC używa Windows Forms, należy ponownie rozpowszechnić mfcmifc80.dll z aplikacją. Aby uzyskać więcej informacji, zobacz [Redystrybuowanie biblioteki MFC](../windows/redistributing-the-mfc-library.md).

## <a name="in-this-section"></a>W tej sekcji

[Hostowanie kontrolki użytkownika formularza systemu Windows w oknie dialogowym MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)

[Hostowanie formantu użytkownika interfejsu Windows Forms jako widoku MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)

[Hostowanie kontrolki użytkownika formularza systemu Windows jako okna dialogowego MFC](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)

## <a name="reference"></a>Dokumentacja

[Klasa CWinFormsControl](../mfc/reference/cwinformscontrol-class.md)

[Klasa CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md)

[Klasa CWinFormsView](../mfc/reference/cwinformsview-class.md)

[ICommandSource, interfejs](../mfc/reference/icommandsource-interface.md)

[ICommandTarget, interfejs](../mfc/reference/icommandtarget-interface.md)

[ICommandUI, interfejs](../mfc/reference/icommandui-interface.md)

[Interfejs IView](../mfc/reference/iview-interface.md)

[CommandHandler](../atl/commandhandler.md)

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)

[Uicheckstate —](../mfc/reference/uicheckstate-enumeration.md)

## <a name="related-sections"></a>Sekcje pokrewne

[Windows Forms](/dotnet/framework/winforms/index)

[Kontrolki Windows Forms](/dotnet/framework/winforms/controls/index)

## <a name="see-also"></a>Zobacz też

[Elementy interfejsu użytkownika](../mfc/user-interface-elements-mfc.md)<br/>
[Widoki formularzy](../mfc/form-views-mfc.md)
