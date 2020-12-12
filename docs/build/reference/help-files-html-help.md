---
description: 'Dowiedz się więcej na temat: pliki pomocy (Pomoc HTML)'
title: Pliki pomocy (Pomoc HTML)
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
ms.openlocfilehash: 0a2b92300683fcc4f0ced365a6750f6e73da10f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191605"
---
# <a name="help-files-html-help"></a>Pliki pomocy (Pomoc HTML)

Następujące pliki są tworzone po dodaniu pomocy w formacie HTML do aplikacji, zaznaczając pole wyboru **Pomoc kontekstowa** , a następnie wybierając **Format pomocy HTML** na stronie [funkcje zaawansowane](../../mfc/reference/advanced-features-mfc-application-wizard.md) Kreatora aplikacji MFC.

|Nazwa pliku|Lokalizacja katalogu|Lokalizacja Eksplorator rozwiązań|Opis|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*. HHP|*Projname*\hlp|pliki Pomocy w formacie HTML|Plik projektu pomocy. Zawiera dane niezbędne do skompilowania plików pomocy do pliku. HXS lub. chm.|
|*Projname*. HHK|*Projname*\hlp|pliki Pomocy w formacie HTML|Zawiera indeks tematów pomocy.|
|*Projname*. HHC|*Projname*\hlp|pliki Pomocy w formacie HTML|Zawartość projektu pomocy.|
|Makehtmlhelp.bat|*Projname*|Pliki źródłowe|Używany przez system do kompilowania projektu pomocy podczas kompilowania projektu.|
|Afxcore.htm|*Projname*\hlp|Tematy pomocy HTML|Zawiera standardowe tematy pomocy dla standardowych poleceń MFC i obiektów ekranu. Dodaj własne tematy pomocy do tego pliku.|
|Afxprint.htm|*Projname*\hlp|Tematy pomocy HTML|Zawiera tematy pomocy dla poleceń drukowania.|
|*. jpg; \*. gif|*Projname*\hlp\Images|Pliki zasobów|Zawiera obrazy dla różnych wygenerowanych tematów pomocy.|

## <a name="see-also"></a>Zobacz też

[Typy plików utworzone dla projektów Visual Studio C++](file-types-created-for-visual-cpp-projects.md)
