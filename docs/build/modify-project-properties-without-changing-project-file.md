---
description: 'Dowiedz się więcej o: jak modyfikować właściwości projektu C++ i obiekty docelowe bez zmiany pliku projektu'
title: 'Instrukcje: modyfikowanie właściwości projektu C++ i elementów docelowych bez zmiany pliku projektu'
ms.date: 11/28/2018
helpviewer_keywords:
- project properties [C++], modifying outside project file
ms.openlocfilehash: 91f71ccf7764307fef174d31a63583d6a3ce2aeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179866"
---
# <a name="how-to-modify-c-project-properties-and-targets-without-changing-the-project-file"></a>Instrukcje: modyfikowanie właściwości projektu C++ i elementów docelowych bez zmiany pliku projektu

Właściwości projektu i obiekty docelowe można przesłonić z poziomu wiersza polecenia programu MSBuild bez zmiany pliku projektu. Jest to przydatne, gdy chcesz tymczasowo lub sporadycznie zastosować pewne właściwości. Założono pewne informacje dotyczące programu MSBuild. Aby uzyskać więcej informacji, zobacz [MSBuild](/visualstudio/msbuild/msbuild).

> [!IMPORTANT]
> Aby utworzyć plik. props lub. targets, można użyć edytora XML w programie Visual Studio lub dowolnego edytora tekstu. Nie używaj **Menedżer właściwości** w tym scenariuszu, ponieważ dodaje właściwości do pliku projektu.

*Aby zastąpić właściwości projektu:*

1. Utwórz plik. props, który określa właściwości, które chcesz przesłonić.

1. W wierszu polecenia: Set ForceImportBeforeCppTargets = "C:\sources\ my_props. props"

*Aby zastąpić cele projektu:*

1. Utwórz plik. targets z ich implementacją lub określonym elementem docelowym

2. W wierszu polecenia: Set ForceImportAfterCppTargets = "C:\sources\ my_target. targets"

Można również ustawić każdą opcję w wierszu polecenia programu MSBuild przy użyciu opcji/p:

```cmd
> msbuild myproject.sln /p:ForceImportBeforeCppTargets="C:\sources\my_props.props"
> msbuild myproject.sln /p:ForceImportAfterCppTargets="C:\sources\my_target.targets"
```

Zastępowanie właściwości i elementów docelowych w ten sposób jest równoznaczne z dodaniem następujących importów do wszystkich plików. vcxproj w rozwiązaniu:

```cmd
<Import Project=="C:\sources\my_props.props" />
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
<Import Project==" C:\sources\my_target.targets"" />
```
