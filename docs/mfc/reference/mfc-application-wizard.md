---
description: 'Dowiedz się więcej na temat: Kreator aplikacji MFC'
title: Kreator aplikacji MFC
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.overview
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
ms.openlocfilehash: 645f0e1ed3f1f35c109d524a8c63fa36231bc61a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219216"
---
# <a name="mfc-application-wizard"></a>Kreator aplikacji MFC

Kreator aplikacji MFC tworzy aplikację, która po skompilowaniu implementuje podstawowe funkcje aplikacji wykonywalnej systemu Windows (.exe). Aplikacja startowa MFC starter zawiera pliki źródłowe (.cpp) języka C++, pliki zasobów (.rc), pliki nagłówków (.h) i pliki projektu (.vcxproj). Kod generowany w tych plikach startowych jest oparty na bibliotece MFC.

> [!NOTE]
> Zależnie od wybranych opcji kreator tworzy dodatkowe pliki w projekcie. Na przykład jeśli na stronie [funkcje zaawansowane](../../mfc/reference/advanced-features-mfc-application-wizard.md) zostanie wybrana opcja **Pomoc kontekstowa** , Kreator utworzy pliki niezbędne do skompilowania plików pomocy projektu. Aby uzyskać więcej informacji na temat plików tworzonych przez kreatora, zobacz [typy plików utworzonych dla projektów Visual Studio C++](../../build/reference/file-types-created-for-visual-cpp-projects.md)i zobacz plik Readme.txt w projekcie.

## <a name="overview"></a>Omówienie

Ta strona kreatora zawiera opis bieżących ustawień tworzonej aplikacji MFC. Domyślnie kreator tworzy projekt w następujący sposób:

- [Typ aplikacji, Kreator aplikacji MFC](../../mfc/reference/application-type-mfc-application-wizard.md)

  - Projekt jest tworzony z obsługą interfejsu kart dla wielu dokumentów (MDI). Aby uzyskać więcej informacji, zobacz [SDI i MDI](../../mfc/sdi-and-mdi.md).

  - Projekt używa [architektury dokumentu/widoku](../../mfc/document-view-architecture.md).

  - Projekt używa bibliotek Unicode.

  - Projekt jest tworzony przy użyciu stylu projektu programu Visual Studio i umożliwia przełączanie stylu wizualnego.

  - Projekt używa biblioteki MFC w udostępnionym pliku DLL. Aby uzyskać więcej informacji, zobacz [tworzenie bibliotek DLL C/C++ w programie Visual Studio](../../build/dlls-in-visual-cpp.md).

- [Obsługa dokumentu złożonego, Kreator aplikacji MFC](../../mfc/reference/compound-document-support-mfc-application-wizard.md)

  - Projekt nie obsługuje dokumentów złożonych.

- [Ciągi szablonu dokumentu, kreator aplikacji MFC](../../mfc/reference/document-template-strings-mfc-application-wizard.md)

  - Nazwa projektu jest używana dla ciągów tekstowych domyślnego szablonu dokumentów.

- [Obsługa bazy danych, Kreator aplikacji MFC](../../mfc/reference/database-support-mfc-application-wizard.md)

  - Projekt nie obsługuje baz danych.

- [Funkcje interfejsu użytkownika, Kreator aplikacji MFC](../../mfc/reference/user-interface-features-mfc-application-wizard.md)

  - Projekt implementuje standardowe funkcje interfejsu użytkownika systemu Windows, takie jak menu systemowe, pasek stanu, zmaksymalizowanie i minimalizowanie pól, pola **informacje** , standardowy pasek menu i zadokowany pasek narzędzi oraz ramki potomne.

- [Funkcje zaawansowane, Kreator aplikacji MFC](../../mfc/reference/advanced-features-mfc-application-wizard.md)

  - Projekt obsługuje drukowanie i podgląd wydruku.

  - Projekt obsługuje kontrolki ActiveX. Aby uzyskać więcej informacji, zobacz [sekwencja operacji tworzenia formantów ActiveX](../../mfc/sequence-of-operations-for-creating-activex-controls.md).

  - Projekt nie obsługuje [automatyzacji](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows Sockets](../../mfc/windows-sockets-in-mfc.md)lub Active Accessibility.

  - Projekt obsługuje okienko dokowania **Eksploratora** , okienko dokowania **danych wyjściowych** i okienko dokowania **Właściwości** .

- [Wygenerowane klasy, Kreator aplikacji MFC](../../mfc/reference/generated-classes-mfc-application-wizard.md)

  - Klasa widoku projektu pochodzi od [klasy CView](../../mfc/reference/cview-class.md).

  - Klasa aplikacji projektu pochodzi od [klasy CWinAppEx](../../mfc/reference/cwinappex-class.md).

  - Klasa dokumentu projektu jest pochodną [klasy CDocument](../../mfc/reference/cdocument-class.md).

  - Klasa głównej ramki projektu pochodzi od [klasy CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md).

  - Klasa podrzędnej ramki projektu pochodzi od [klasy CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md).

Aby zmienić te domyślne ustawienia, należy kliknąć odpowiedni tytuł karty w lewej kolumnie kreatora i wprowadź zmiany na wyświetlonej stronie.

Po utworzeniu projektu aplikacji MFC można dodać obiekty lub kontrolki do projektu za pomocą [kreatorów kodu](../../ide/adding-functionality-with-code-wizards-cpp.md)Visual C++.

## <a name="see-also"></a>Zobacz też

[Tworzenie aplikacji MFC](../../mfc/reference/creating-an-mfc-application.md)<br/>
[Aplikacje klasyczne MFC](../../mfc/mfc-desktop-applications.md)<br/>
[Używanie klas do pisania aplikacji dla systemu Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)
