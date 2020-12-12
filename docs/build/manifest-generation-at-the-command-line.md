---
description: 'Dowiedz się więcej na temat: generowanie manifestu w wierszu polecenia'
title: Generowanie manifestu w wierszu polecenia
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
ms.openlocfilehash: 30b826e0fe98a143f58d7987203881a8fd8e601b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176460"
---
# <a name="manifest-generation-at-the-command-line"></a>Generowanie manifestu w wierszu polecenia

Podczas kompilowania aplikacji C/C++ z wiersza polecenia przy użyciu NMAKE lub podobnych narzędzi, Manifest jest generowany po przetworzeniu wszystkich plików obiektów i skompilowaniu końcowego pliku binarnego przez konsolidator. Konsolidator zbiera informacje zestawu przechowywane w plikach obiektów i łączy te informacje w końcowy plik manifestu. Domyślnie konsolidator generuje plik o nazwie *binary_name*. *Extension*. manifest, aby opisać końcowy plik binarny. Konsolidator nie osadza pliku manifestu wewnątrz danych binarnych i może generować tylko manifest jako plik zewnętrzny. Istnieje kilka sposobów osadzenia manifestu w końcowym pliku binarnym, na przykład przy użyciu [narzędzia manifestu (mt.exe)](/windows/win32/sbscs/mt-exe) lub kompilowania manifestu w plik zasobów. Należy pamiętać, że po osadzeniu manifestu w końcowym pliku binarnym należy przestrzegać określonych reguł, aby umożliwić takie funkcje jak łączenie przyrostowe, podpisywanie i edytowanie i kontynuowanie. Te i inne opcje zostały omówione w temacie [: osadzanie manifestu w aplikacji C/C++](how-to-embed-a-manifest-inside-a-c-cpp-application.md) podczas kompilowania w wierszu polecenia.

## <a name="see-also"></a>Zobacz też

[Manifesty](/windows/win32/sbscs/manifests)<br/>
[/INCREMENTAL (łącz przyrostowo)](reference/incremental-link-incrementally.md)<br/>
[Zestawy o silnych nazwach (podpisywanie zestawów) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[Edytuj i kontynuuj](/visualstudio/debugger/edit-and-continue)<br/>
[Informacje o generowaniu manifestu dla programów C/C++](understanding-manifest-generation-for-c-cpp-programs.md)<br/>
