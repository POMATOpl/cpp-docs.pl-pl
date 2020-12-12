---
description: 'Dowiedz się więcej na temat: pliki projektu i rozwiązania'
title: Pliki projektu i rozwiązania
ms.date: 05/06/2019
helpviewer_keywords:
- project files [C++]
- file types [C++], makefiles
- .sdf, browsing database file
- Makefile projects
- browsing database file, .sdf
- file types [C++], project files
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
ms.openlocfilehash: e91876f1c405b8a145e0a2d94195a424101b469b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225781"
---
# <a name="project-and-solution-files"></a>Pliki projektu i rozwiązania

Następujące pliki są tworzone podczas tworzenia projektu w programie Visual Studio. Są one używane do zarządzania plikami projektu w rozwiązaniu.

|Nazwa pliku|Lokalizacja katalogu|Lokalizacja Eksplorator rozwiązań|Opis|
|--------------|------------------------|--------------------------------|-----------------|
|*Solname*. sln|*Projname*|Niewyświetlane w Eksplorator rozwiązań|Plik *rozwiązania* . Organizuje wszystkie elementy projektu lub wiele projektów w jednym rozwiązaniu.|
|*Projname*. suo|*Projname*|Niewyświetlane w Eksplorator rozwiązań|Plik *opcji rozwiązania* . Przechowuje Twoje dostosowania dla rozwiązania, aby przy każdym otwarciu projektu lub pliku w rozwiązaniu miało on wygląd i zachowanie.|
|*Projname*. vcxproj|*Projname*|Niewyświetlane w Eksplorator rozwiązań|Plik *projektu* . Przechowuje informacje specyficzne dla każdego projektu. (We wcześniejszych wersjach ten plik miał nazwę *Projname*. vcproj lub *Projname*. DSP). Przykład pliku projektu C++ (. vcxproj), zobacz [pliki projektu](project-files.md).|
|*Projname*. vcxitems|*Projname*|Niewyświetlane w Eksplorator rozwiązań|Plik *projektu elementy udostępnione* . Ten projekt nie został skompilowany.  Zamiast tego projekt może być przywoływany przez inny projekt języka C++, a jego pliki staną się częścią procesu kompilacji odwołującego się projektu. Może to służyć do udostępniania wspólnego kodu za pomocą międzyplatformowych projektów języka C++.|
|*Projname*. sdf|*Projname*|Niewyświetlane w Eksplorator rozwiązań|Plik *bazy danych przeglądania* . Obsługuje funkcje przeglądania i nawigowania, takie jak **Definicja goto**, **Znajdowanie wszystkich odwołań** i **Widok klasy**. Jest on generowany przez analizowanie plików nagłówkowych.|
|*Projname*. vcxproj. filters|*Projname*|Niewyświetlane w Eksplorator rozwiązań|Plik *filtrów* . Określa miejsce umieszczenia pliku, który jest dodawany do rozwiązania. Na przykład plik. h jest umieszczany w węźle **pliki nagłówkowe** .|
|*Projname*. vcxproj. User|*Projname*|Niewyświetlane w Eksplorator rozwiązań|Plik *użytkownika migracji* . Po przeprowadzeniu migracji projektu z programu Visual Studio 2008 ten plik zawiera informacje, które zostały skonwertowane z dowolnego pliku. VSPROPS.|
|*Projname*. idl|*Projname*|Źródło|(Specyficzne dla projektu) Zawiera kod źródłowy języka opisu interfejsu (IDL) dla biblioteki typów kontrolek. Ten plik jest używany przez Visual C++ do wygenerowania biblioteki typów. Wygenerowana Biblioteka uwidacznia interfejs kontroli innym klientom automatyzacji. Aby uzyskać więcej informacji, zobacz [plik definicji interfejsu (IDL)](/windows/win32/Rpc/the-interface-definition-language-idl-file) w Windows SDK.|
|Readme.txt|*Projname*|Project|Plik do *odczytu* . Jest on generowany przez Kreatora aplikacji i opisuje pliki w projekcie.|

## <a name="see-also"></a>Zobacz też

[Typy plików utworzone dla projektów Visual Studio C++](file-types-created-for-visual-cpp-projects.md)
