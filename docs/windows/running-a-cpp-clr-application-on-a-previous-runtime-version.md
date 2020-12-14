---
description: 'Dowiedz się więcej na temat: uruchamianie aplikacji C++/CLR w poprzedniej wersji środowiska uruchomieniowego'
title: Uruchamianie aplikacji języka C++ dla środowiska CLR w poprzedniej wersji środowiska uruchomieniowego
ms.date: 11/04/2016
helpviewer_keywords:
- applications [C++], runtime version specified
- versions [C++]
- app.config files, runtime version specified
- compatibility [C++], runtime version specified
- backward compatibility [C++], runtime version specified
- application deployment [C++], runtime version specified
- common language runtime [C++], version specified
- deploying applications [C++], runtime version specified
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
ms.openlocfilehash: 3b1bbc2906e4b347bb954c799cb9e412202a17ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247218"
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>Uruchamianie aplikacji C++/clr w poprzedniej wersji środowiska uruchomieniowego

O ile nie określono inaczej, aplikacja C++ .NET Framework jest skompilowana do uruchamiania w wersji środowiska uruchomieniowego języka wspólnego (CLR) używanej przez kompilator do kompilowania aplikacji. Jednak jest możliwe, aby aplikacja. exe skompilowana dla jednej wersji środowiska uruchomieniowego działała w dowolnej innej wersji, która zapewnia wymagane funkcje.

Aby to osiągnąć, podaj plik app.config, który zawiera informacje o wersji środowiska uruchomieniowego w `supportedRuntime` tagu.

W czasie wykonywania plik app.config musi mieć nazwę w postaci *filename. ext*. config, gdzie *filename. ext* jest nazwą pliku wykonywalnego, który uruchomił aplikację, i musi znajdować się w tym samym katalogu, w którym znajduje się plik wykonywalny. Na przykład jeśli aplikacja ma nazwę TestApp.exe, plik app.config będzie miał nazwę TestApp.exe.config.

W przypadku określenia więcej niż jednej wersji środowiska uruchomieniowego i uruchomienia aplikacji na komputerze, na którym jest zainstalowana więcej niż jedna wersja środowiska uruchomieniowego, aplikacja używa pierwszej wersji, która jest określona w pliku konfiguracji i jest zainstalowana.

## <a name="see-also"></a>Zobacz też

[Wdrażanie aplikacji klasycznych](deploying-native-desktop-applications-visual-cpp.md)
