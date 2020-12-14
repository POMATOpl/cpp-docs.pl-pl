---
description: 'Dowiedz się więcej na temat: pliki utworzone dla projektów CLR'
title: Pliki utworzone dla projektów CLR
ms.date: 11/04/2016
helpviewer_keywords:
- Visual Studio C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
ms.openlocfilehash: 14aa07d891a75307f119f33ace5c32dbb2aa18db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200529"
---
# <a name="files-created-for-clr-projects"></a>Pliki utworzone dla projektów CLR

W przypadku tworzenia projektów za pomocą szablonów Visual C++, w zależności od używanego szablonu, tworzone są kilka plików. W poniższej tabeli wymieniono wszystkie pliki, które są tworzone przez szablony projektu dla projektów .NET Framework.

|Nazwa pliku|Opis pliku|
|---------------|----------------------|
|AssemblyInfo. cpp|Plik zawierający informacje (czyli atrybuty, pliki, zasoby, typy, informacje o wersji, informacje o podpisywaniu itd.) w celu zmodyfikowania metadanych zestawu projektu. Aby uzyskać więcej informacji, zobacz [pojęcia związane z zestawem](/dotnet/framework/app-domains/assembly-contents).|
|*Projname*. asmx|Plik tekstowy, który odwołuje się do zarządzanych klas, które hermetyzują funkcjonalność usługi sieci Web XML.|
|*Projname*. cpp|Główny plik źródłowy i punkt wejścia do aplikacji utworzonej przez program Visual Studio. Identyfikuje plik Project. dll i przestrzeń nazw projektu. Podaj własny kod w tym pliku.|
|*Projname*. vsdisco|Plik wdrożenia XML zawierający linki do innych zasobów, które opisują usługę sieci Web XML.|
|*Projname*. h|Główny plik dołączania dla projektu, który zawiera wszystkie deklaracje, symbole globalne i `#include` dyrektywy dla innych plików nagłówkowych.|
|*Projname*. sln|Plik rozwiązania używany w środowisku deweloperskim do organizowania wszystkich elementów projektu w jednym rozwiązaniu.|
|*Projname*. suo|Plik opcji rozwiązania używany w środowisku programistycznym.|
|*Projname*. vcxproj|Plik projektu używany w środowisku deweloperskim, w którym przechowywane są informacje specyficzne dla tego projektu.|
|ReadMe.txt|Plik opisujący każdy plik w projekcie przy użyciu rzeczywistych nazw plików utworzonych przez szablon.|
