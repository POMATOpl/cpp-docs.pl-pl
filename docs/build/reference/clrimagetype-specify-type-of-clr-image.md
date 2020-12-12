---
description: Dowiedz się więcej o:/CLRIMAGETYPE (Określ typ obrazu CLR)
title: /CLRIMAGETYPE (Określenie typu obrazu CLR)
ms.date: 05/16/2019
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
ms.openlocfilehash: 7c499eeddcacd674a9dfc2134e059fd8b3b9a6b6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179151"
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (Określenie typu obrazu CLR)

Ustaw typ obrazu CLR w połączonym obrazie.

## <a name="syntax"></a>Składnia

> **/CLRIMAGETYPE:**{ | **SAFE32BITPREFERRED Pure** | **bezpieczne** | 

## <a name="remarks"></a>Uwagi

Konsolidator akceptuje obiekty natywne, a także obiekty MSIL, które są kompilowane przy użyciu [/CLR](clr-common-language-runtime-compilation.md). **/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego zostały zaniechane w programie Visual Studio 2015 i nie są obsługiwane w programie Visual Studio 2017 lub nowszym. Po przekazaniu mieszanych obiektów w tej samej kompilacji, zweryfikowanie wynikowego pliku wyjściowego jest domyślnie równe najniższyemu poziomowi weryfikacji modułów wejściowych. Na przykład w przypadku przekazania obrazu natywnego i obrazu w trybie mieszanym (skompilowane przy użyciu **/CLR**) obraz wyników będzie obrazem trybu mieszanego.

Możesz użyć **/CLRIMAGETYPE** , aby określić niższy poziom weryfikacji, jeśli jest to potrzebne.

Aby uzyskać informacje na temat sposobu określania typu obrazu CLR dla pliku, zobacz [/CLRHEADER](clrheader.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń węzeł **Właściwości konfiguracji** .

1. Rozwiń węzeł **konsolidatora** .

1. Wybierz stronę właściwości **Zaawansowane** .

1. Zmodyfikuj właściwość **Typ obrazu CLR** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.

## <a name="see-also"></a>Zobacz też

- [Dokumentacja konsolidatora MSVC](linking.md)
- [MSVC Opcje konsolidatora](linker-options.md)
