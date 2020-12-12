---
description: 'Dowiedz się więcej na temat: Strona właściwości zasobów zarządzanych'
title: Strona właściwości Zarządzane zasoby
ms.date: 08/28/2019
f1_keywords:
- VC.Project.VCManagedResourceCompilerTool.ResourceFileName
- VC.Project.VCManagedResourceCompilerTool.OutputFileName
- VC.Project.VCManagedResourceCompilerTool.DefaultLocalizedResources
helpviewer_keywords:
- Managed Resources property page
ms.assetid: 80b80384-ee55-494d-9f0e-907bb98cfc19
ms.openlocfilehash: 42816e2b4625bc5ab4620f4caafb627f55bd9cd5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190721"
---
# <a name="managed-resources-property-page"></a>Strona właściwości Zarządzane zasoby

Na stronie właściwości **zarządzane zasoby** są ujawniane następujące właściwości kompilatora zasobów zarządzanych [resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) w przypadku używania zasobów platformy .NET w programach C++/CLI:

- **Nazwa logiczna zasobu**

   Określa *nazwę logiczną* wygenerowanego pośredniego pliku Resources. Nazwa logiczna to nazwa używana do ładowania zasobu. Jeśli nie określono nazwy logicznej, nazwa pliku zasobu (. resx) jest używana jako nazwa logiczna.

- **Nazwa pliku wyjściowego**

   Określa nazwę końcowego pliku wyjściowego, do którego wchodzi plik zasobu (. resx).

- **Domyślne zlokalizowane zasoby**

   Określa, czy dany plik resx wchodzi w skład domyślnych zasobów, czy do pliku satelickiego. dll.

Aby uzyskać informacje na temat uzyskiwania dostępu do strony właściwości **zarządzane zasoby** , zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

## <a name="see-also"></a>Zobacz też

[Korzystanie z RC (wiersz polecenia RC)](/windows/win32/menurc/using-rc-the-rc-command-line-)<br>
[Odwołanie do strony właściwości projektu C++](property-pages-visual-cpp.md)<br>
[/ASSEMBLYRESOURCE (Osadź zarządzany zasób)](assemblyresource-embed-a-managed-resource.md)
