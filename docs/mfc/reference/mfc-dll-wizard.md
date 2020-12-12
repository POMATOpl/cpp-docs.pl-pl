---
description: 'Dowiedz się więcej na temat: Kreator biblioteki MFC DLL'
title: Kreator biblioteki MFC DLL
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.dll.overview
helpviewer_keywords:
- MFC DLLs [MFC], creating
- MFC DLL Wizard
- DLLs [MFC], MFC
- DLL wizard [MFC]
- MFC DLLs [MFC]
- DLLs [MFC], creating
ms.assetid: 4e936031-7e39-4f40-a295-42a09c5ff264
ms.openlocfilehash: 0f786255c22e644335c5154e0f14add59a2a418a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219164"
---
# <a name="mfc-dll-wizard"></a>Kreator biblioteki MFC DLL

W przypadku tworzenia projektu biblioteki MFC DLL przy użyciu kreatora MFC DLL można uzyskać działającą aplikację startową z wbudowaną funkcją, która po skompilowaniu spowoduje zaimplementowanie podstawowych funkcji [biblioteki DLL](../../build/dlls-in-visual-cpp.md). Program Starter MFC zawiera pliki źródłowe (. cpp) języka C++, pliki zasobów (. RC) i plik projektu (. vcxproj). Kod wygenerowany w tych starterach plików jest oparty na MFC. Aby uzyskać bardziej szczegółowe informacje, zobacz szczegóły pliku w Readme.txt, który jest generowany dla projektu w programie Visual Studio, oraz [klasy i funkcje generowane przez kreatora MFC DLL](../../mfc/reference/classes-and-functions-generated-by-the-mfc-dll-wizard.md)

## <a name="overview"></a>Omówienie

Ta strona kreatora zawiera opis bieżących [ustawień aplikacji dla tworzonego projektu DLL MFC](../../mfc/reference/application-settings-mfc-dll-wizard.md) . Domyślnie projekt jest tworzony jako zwykły projekt MFC DLL (MFC Shared) bez dodatkowych ustawień.

Aby zmienić te ustawienia domyślne, kliknij pozycję **Ustawienia aplikacji** w lewej kolumnie kreatora i wprowadź zmiany na tej stronie kreatora MFC DLL.

Po utworzeniu projektu MFC DLL można dodać obiekty lub kontrolki do projektu za pomocą [kreatorów kodu](../../ide/adding-functionality-with-code-wizards-cpp.md)Visual C++.

Można wykonać następujące zadania i typy ulepszeń do podstawowego projektu MFC DLL:

- [Eksportuj z biblioteki DLL](../../build/exporting-from-a-dll.md)

- [Łączenie pliku wykonywalnego z biblioteką DLL](../../build/linking-an-executable-to-a-dll.md)

- [Inicjowanie biblioteki DLL](../../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="see-also"></a>Zobacz też

[Projekty programu Visual Studio — C++](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[Strony właściwości](../../build/reference/property-pages-visual-cpp.md)<br/>
[Ustawianie właściwości kompilatora i Build](../../build/working-with-project-properties.md)<br/>
[Klasa MFC](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Dodawanie funkcji członkowskiej](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Implementowanie interfejsu](../../ide/implementing-an-interface-visual-cpp.md)<br/>
