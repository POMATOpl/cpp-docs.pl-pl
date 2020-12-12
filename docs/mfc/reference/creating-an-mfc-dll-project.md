---
description: 'Dowiedz się więcej na temat: Tworzenie projektu MFC DLL'
title: Tworzenie projektu MFC DLL
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.mfcdll.project
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
ms.openlocfilehash: 5a91fadf38a2891ad93c35457a2013bbb81f449b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301194"
---
# <a name="creating-an-mfc-dll-project"></a>Tworzenie projektu MFC DLL

Biblioteka MFC DLL to plik binarny, który działa jako udostępniona biblioteka funkcji, które mogą być używane jednocześnie przez wiele aplikacji. Najprostszym sposobem tworzenia projektu MFC DLL jest użycie kreatora MFC DLL.

> [!NOTE]
> Wygląd funkcji w IDE może zależeć od ustawień aktywnych lub wydania i może się różnić od tych opisanych w pomocy. Aby zmienić ustawienia, wybierz **Importuj i Eksportuj ustawienia** w menu **Narzędzia** . Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>Aby utworzyć projekt MFC DLL przy użyciu kreatora MFC DLL

1. Postępuj zgodnie z instrukcjami podanymi w temacie dotyczącym [tworzenia aplikacji MFC](creating-an-mfc-application.md) , ale z listy dostępnych szablonów wybierz opcję **biblioteka dołączana dynamicznie MFC** lub biblioteka **MFC DLL** .

1. Zdefiniuj ustawienia aplikacji, korzystając ze strony [Ustawienia aplikacji](../../mfc/reference/application-settings-mfc-dll-wizard.md) [kreatora MFC DLL](../../mfc/reference/mfc-dll-wizard.md).

    > [!NOTE]
    >  Pomiń ten krok, aby zachować ustawienia domyślne kreatora.

1. Kliknij przycisk **Zakończ** , aby zamknąć kreatora i otworzyć nowy projekt w **Eksplorator rozwiązań**.

Po utworzeniu projektu można wyświetlić pliki utworzone w **Eksplorator rozwiązań**. Aby uzyskać więcej informacji na temat plików tworzonych przez kreatora dla projektu, zobacz plik wygenerowany przez projekt ReadMe.txt. Aby uzyskać więcej informacji na temat typów plików, zobacz [typy plików utworzonych dla projektów Visual Studio C++](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Zobacz też

[Typy projektów C++ w programie Visual Studio](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[Dodawanie funkcji za pomocą kreatorów kodu](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Strony właściwości](../../build/reference/property-pages-visual-cpp.md)
