---
description: 'Dowiedz się więcej o programie: Rozwiązywanie problemów z dostosowywaniem kompilacji'
title: Rozwiązywanie problemów z dostosowaniami kompilacji
ms.date: 11/04/2016
helpviewer_keywords:
- build events [C++], troubleshooting
- builds [C++], build events
- troubleshooting [C++], builds
- build steps [C++], troubleshooting
- events [C++], build
- builds [C++], troubleshooting
- custom build steps [C++], troubleshooting
ms.assetid: e4ceb177-fbee-4ed3-a7d7-80f0d78c1d07
ms.openlocfilehash: e75dfeb32caf8c9c712c06b9dfb9e71f3e3c29b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277443"
---
# <a name="troubleshooting-build-customizations"></a>Rozwiązywanie problemów z dostosowaniami kompilacji

Jeśli niestandardowe kroki lub zdarzenia kompilacji nie działają zgodnie z oczekiwaniami, istnieje kilka rzeczy, które można wykonać, aby dowiedzieć się, co się stało.

- Upewnij się, że pliki, które są generowane przez niestandardowe kroki kompilacji, są zgodne z plikami, które deklarujesz jako dane wyjściowe.

- Jeśli niestandardowe kroki kompilacji generują wszystkie pliki, które są danymi wejściowymi lub zależnościami innych kroków kompilacji (niestandardowe lub w inny sposób), należy się upewnić, że te pliki są dodawane do projektu. Upewnij się, że narzędzia, które zużywają te pliki, są wykonywane po kroku kompilacji niestandardowej.

- Aby wyświetlić informacje o tym, co robi niestandardowy krok kompilacji, Dodaj `@echo on` jako pierwsze polecenie. Zdarzenia kompilacji i kroki kompilacji są umieszczane w tymczasowym pliku. bat i uruchamiane po skompilowaniu projektu. W związku z tym można dodać sprawdzanie błędów do zdarzenia kompilacji lub kroku kompilacji.

- Sprawdź dziennik kompilacji w katalogu plików pośrednich, aby zobaczyć, co faktycznie zostało wykonane. Ścieżka i nazwa dziennika kompilacji są reprezentowane przez wyrażenie makro **MSBuild** **$ (IntDir) \\ $ (MSBuildProjectName). log**.

- Zmodyfikuj ustawienia projektu w taki sposób, aby gromadzić więcej niż domyślną ilość informacji w dzienniku kompilacji. W menu **Tools** (Narzędzia) kliknij pozycję **Options** (Opcje). W oknie dialogowym **Opcje** kliknij węzeł **projekty i rozwiązania** , a następnie kliknij węzeł **kompilacja i uruchomienie** . Następnie w polu **szczegółowości pliku dziennika kompilacji projektu programu MSBuild** kliknij przycisk **szczegóły**.

- Sprawdź wartości wszystkich używanych nazw plików lub makr katalogów. Makra można echo pojedynczo lub dodać `copy %0 command.bat` do początku niestandardowego kroku kompilacji, który skopiuje polecenia niestandardowego kroku kompilacji do command.bat ze wszystkimi rozwiniętymi makrami.

- Uruchom niestandardowe kroki kompilacji i twórz zdarzenia indywidualnie, aby sprawdzić ich zachowanie.

## <a name="see-also"></a>Zobacz też

[Ogólne informacje o niestandardowych krokach budowania lub zdarzeniach kompilacji](understanding-custom-build-steps-and-build-events.md)
