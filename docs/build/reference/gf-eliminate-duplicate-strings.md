---
description: Dowiedz się więcej na temat:/GF (eliminowanie ciągów zduplikowanych)
title: /GF (Eliminowanie ciągów zduplikowanych)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
ms.openlocfilehash: 65c8cca610b9e01cf49939c2074a698b00c6e338
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191943"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (Eliminowanie ciągów zduplikowanych)

Umożliwia kompilatorowi utworzenie pojedynczej kopii identycznych ciągów w obrazie programu i w pamięci podczas wykonywania. Jest to Optymalizacja nazywana *buforowaniem ciągów* , która może tworzyć mniejsze programy.

## <a name="syntax"></a>Składnia

```
/GF
```

## <a name="remarks"></a>Uwagi

Jeśli używasz **/GF**, system operacyjny nie zamienia części ciągu pamięci i może odczytywać ciągi z powrotem z pliku obrazu.

**/GF** pule ciągów jako tylko do odczytu. Jeśli spróbujesz zmodyfikować ciągi w obszarze **/GF**, wystąpi błąd aplikacji.

Buforowanie ciągów pozwala na to, co było przeznaczone jako wiele wskaźników do wielu buforów, aby można było wiele wskaźników do jednego buforu. W poniższym kodzie `s` i `t` są inicjowane z tym samym ciągiem. Buforowanie ciągów powoduje, że wskazują one na tę samą pamięć:

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
> Opcja [/Zi](z7-zi-zi-debug-information-format.md) używana do edycji i kontynuowania powoduje automatyczne ustawienie opcji **/GF** .

> [!NOTE]
> Opcja kompilatora **/GF** tworzy sekcję adresowaną dla każdego unikatowego ciągu. Domyślnie plik obiektu może zawierać do 65 536 sekcji do adresowania. Jeśli program zawiera więcej niż 65 536 ciągów, użyj opcji kompilatora [/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md) , aby utworzyć więcej sekcji.

**/GF** obowiązuje, gdy używany jest [/O1](o1-o2-minimize-size-maximize-speed.md) lub [/O2](o1-o2-minimize-size-maximize-speed.md) .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **generowanie kodu** .

1. Zmodyfikuj właściwość **Włącz buforowanie ciągów** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
