---
description: Dowiedz się więcej na temat:/NODEFAULTLIB (Ignoruj biblioteki)
title: /NODEFAULTLIB (Ignoruj biblioteki)
ms.date: 03/26/2019
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
ms.openlocfilehash: 1443d7ac1e17d464baa829d8297234ae80f3b998
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196714"
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (Ignoruj biblioteki)

> **/NODEFAULTLIB**[__:__*Biblioteka*]

## <a name="arguments"></a>Argumenty

*biblioteki*<br/>
Biblioteka, która ma być ignorowana przez konsolidator, gdy rozwiązuje odwołania zewnętrzne.

## <a name="remarks"></a>Uwagi

Opcja/NODEFAULTLIB informuje konsolidator, aby usunął co najmniej jedną domyślną bibliotekę z listy bibliotek przeszukiwanych podczas rozpoznawania odwołań zewnętrznych.

Aby utworzyć plik. obj, który nie zawiera odwołań do bibliotek domyślnych, użyj [/zl (Pomiń domyślną nazwę biblioteki)](zl-omit-default-library-name.md).

Domyślnie/NODEFAULTLIB usuwa wszystkie biblioteki domyślne z listy bibliotek przeszukiwanych podczas rozpoznawania odwołań zewnętrznych. Opcjonalny parametr *biblioteki* pozwala usunąć określoną bibliotekę z listy bibliotek przeszukiwanych podczas rozpoznawania odwołań zewnętrznych. Określ jedną opcję/NODEFAULTLIB dla każdej biblioteki, która ma zostać wykluczona.

Konsolidator rozpoznaje odwołania do definicji zewnętrznych przez wyszukanie najpierw w bibliotekach, które zostały jawnie określone, a następnie w domyślnych bibliotekach określonych za pomocą opcji [/DEFAULTLIB:](defaultlib-specify-default-library.md) , a następnie w bibliotekach domyślnych o nazwach w plikach obj.

/NODEFAULTLIB:*Biblioteka* zastępuje/DEFAULTLIB:*Library* , gdy ta sama nazwa *biblioteki* jest określona w obu.

Jeśli używasz/NODEFAULTLIB do kompilowania programu bez biblioteki wykonawczej C, może być również konieczne użycie [/entry](entry-entry-point-symbol.md) do określenia funkcji punktu wejścia w programie. Aby uzyskać więcej informacji, zobacz [funkcje biblioteki CRT](../../c-runtime-library/crt-library-features.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >    >  stronę właściwości **dane wejściowe** konsolidatora właściwości konfiguracji.

1. Wybierz właściwość **Ignoruj wszystkie biblioteki domyślne** . Możesz też określić listę oddzielonych średnikami bibliotek, które mają być ignorowane w właściwości **Ignorowanie określonych bibliotek domyślnych** . Na stronie właściwości **wiersza polecenia** zostanie wyświetlony efekt zmian wprowadzonych w tych właściwościach.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> i <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A> .

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
