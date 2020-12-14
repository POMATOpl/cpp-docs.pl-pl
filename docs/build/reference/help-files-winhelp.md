---
description: 'Dowiedz się więcej na temat: pliki pomocy (WinHelp)'
title: Pliki pomocy (WinHelp)
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
ms.openlocfilehash: 77d00154db762d11e064fe91681b81fbe859e7be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200055"
---
# <a name="help-files-winhelp"></a>Pliki pomocy (WinHelp)

Następujące pliki są tworzone po dodaniu typu programu WinHelp pomocy technicznej do aplikacji, zaznaczając pole wyboru **Pomoc kontekstowa** , a następnie wybierając opcję **Format WinHelp** na stronie [funkcje zaawansowane](../../mfc/reference/advanced-features-mfc-application-wizard.md) Kreatora aplikacji MFC.

|Nazwa pliku|Lokalizacja katalogu|Lokalizacja Eksplorator rozwiązań|Opis|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*. hpj|*Projname*\hlp|Pliki źródłowe|Plik projektu pomocy używany przez kompilator pomocy do tworzenia pliku pomocy programu lub kontrolki.|
|*Projname*. rtf|*Projname*\hlp|Pliki pomocy|Zawiera tematy szablonów, które można edytować i informacje o dostosowywaniu pliku. hpj.|
|*Projname*. CNT|*Projname*\hlp|Pliki pomocy|Udostępnia strukturę okna **zawartość** w pomocy systemu Windows.|
|Makehelp.bat|*Projname*|Pliki źródłowe|Używany przez system do kompilowania projektu pomocy podczas kompilowania projektu.|
|Print. rtf|*Projname*\hlp|Pliki pomocy|Tworzony, jeśli projekt zawiera obsługę drukowania (wartość domyślna). Opisuje polecenia drukowania i okna dialogowe.|
|*. bmp|*Projname*\hlp|Pliki zasobów|Zawiera obrazy dla różnych wygenerowanych tematów pomocy.|

Obsługę funkcji WinHelp można dodać do projektu kontrolki ActiveX MFC, wybierając pozycję **Generuj pliki pomocy** na karcie [Ustawienia aplikacji](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) kreatora kontrolek ActiveX MFC. Następujące pliki są dodawane do projektu po dodaniu pomocy technicznej do kontrolki ActiveX MFC:

|Nazwa pliku|Lokalizacja katalogu|Lokalizacja Eksplorator rozwiązań|Opis|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*. hpj|*Projname*\hlp|Pliki źródłowe|Plik projektu używany przez kompilator pomocy do tworzenia pliku pomocy programu lub kontrolki.|
|*Projname*. rtf|*Projname*\hlp|Project|Zawiera tematy szablonów, które można edytować i informacje o dostosowywaniu pliku. hpj.|
|Makehelp.bat|*Projname*|Pliki źródłowe|Używany przez system do kompilowania projektu pomocy podczas kompilowania projektu.|
|Bullet.bmp|*Projname*|Pliki zasobów|Używany przez standardowe tematy pliku pomocy do reprezentowania list punktowanych.|

## <a name="see-also"></a>Zobacz też

[Typy plików utworzone dla projektów Visual Studio C++](file-types-created-for-visual-cpp-projects.md)
