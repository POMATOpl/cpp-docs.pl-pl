---
description: 'Dowiedz się więcej o: Strona właściwości NMake'
title: Strona właściwości NMake (Windows C++) | Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
helpviewer_keywords:
- NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
ms.openlocfilehash: 58256ad8542e7d411769efb661970f9c41797ec3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196805"
---
# <a name="nmake-property-page"></a>Strona właściwości NMake

Strona właściwości **NMAKE** umożliwia określenie ustawień kompilacji dla projektów NMAKE. (NMAKE to implementacja firmy [Microsoft.)](https://wikipedia.org/wiki/Make_(software))

Aby uzyskać więcej informacji na temat projektów NMake, zobacz [Tworzenie projektu pliku reguł programu make](creating-a-makefile-project.md). W przypadku projektów z regułami Make systemu Windows, zobacz [właściwości projektu pliku reguł programu make (Linux c++)](../../linux/prop-pages/makefile-linux.md), [Ogólne właściwości projektu (Windows c++ make)](/visualstudio/cross-platform/general-makefile-android-prop-page) lub [Właściwości NMAKE (Android c++)](/visualstudio/cross-platform/nmake-android-prop-page).

Strona właściwości **NMAKE** zawiera następujące właściwości.

## <a name="uielement-list"></a>Lista elementów UI

- **Wiersz polecenia kompilacji**

   Określa polecenie, które ma być uruchamiane po kliknięciu **kompilacji** w menu **kompilacja** .

- **Kompiluj ponownie wszystkie wiersze polecenia**

   Określa polecenie, które ma być uruchamiane po kliknięciu przycisku Kompiluj **ponownie wszystko** w menu **kompilacja** .

- **Wyczyść wiersz polecenia**

   Określa polecenie, które ma być uruchamiane po kliknięciu przycisku **Wyczyść** w menu **kompilacja** .

- **Dane wyjściowe**

   Określa nazwę pliku, który będzie zawierać dane wyjściowe dla wiersza polecenia. Domyślnie ta nazwa pliku jest oparta na nazwie projektu.

- **Definicje preprocesora**

   Określa Definicje preprocesora używane przez pliki źródłowe. Wartość domyślna jest określana przez bieżącą platformę i konfigurację.

- **Ścieżka wyszukiwania dołączania**

   Określa katalogi, w których Kompilator wyszukuje pliki dołączane.

- **Wymuszone dołączenia**

   Określa pliki, które preprocesor automatycznie przetwarza, nawet jeśli nie znajdują się one w plikach projektu.

- **Ścieżka wyszukiwania zestawu**

   Określa katalogi, w których .NET Framework jest wyszukiwany, gdy Trys do rozpoznania zestawów .NET.

- **Wymuszone używanie zestawów**

   Określa zestawy, które są automatycznie przetwarzane przez .NET Framework.

- **Opcje dodatkowe**

   Określa dodatkowe przełączniki kompilatora, które mają być używane przez funkcję IntelliSense podczas analizowania plików C++.

Aby uzyskać informacje o sposobach uzyskiwania dostępu do strony właściwości **NMAKE** , zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

Aby uzyskać informacje o sposobach programistycznego dostępu do elementów członkowskich tego obiektu, zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool> .

## <a name="see-also"></a>Zobacz też

[Odwołanie do strony właściwości projektu C++](property-pages-visual-cpp.md)<br>
