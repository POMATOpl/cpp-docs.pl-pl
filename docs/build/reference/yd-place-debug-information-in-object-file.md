---
description: Dowiedz się więcej na temat:/YD (Umieść informacje o debugowaniu w pliku obiektu)
title: /Yd (Umieść informacje o debugowaniu w pliku obiektu)
ms.date: 11/04/2016
f1_keywords:
- /yd
helpviewer_keywords:
- /Yd compiler option [C++]
- -Yd compiler option [C++]
- debugging [C++], debug information files
- Yd compiler option [C++]
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
ms.openlocfilehash: 7716d5ca1893faefac9186f97e2f7439a3887343
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243591"
---
# <a name="yd-place-debug-information-in-object-file"></a>/Yd (Umieść informacje o debugowaniu w pliku obiektu)

Tępy pełne informacje o debugowaniu we wszystkich plikach obiektów utworzonych na podstawie prekompilowanego pliku nagłówkowego (. pch), gdy jest używany z opcjami [/YC](yc-create-precompiled-header-file.md) i [/Z7](z7-zi-zi-debug-information-format.md) . Przestarzałe.

## <a name="syntax"></a>Składnia

```
/Yd
```

## <a name="remarks"></a>Uwagi

**/YD** jest przestarzała; Visual C++ teraz obsługuje wiele obiektów do zapisu w pojedynczym pliku. pdb, zamiast tego należy użyć **/Zi** . Aby zapoznać się z listą przestarzałych opcji kompilatora, zobacz Opcje kompilatora **przestarzałe i usunięte** w [opcjach kompilatora wymienionych według kategorii](compiler-options-listed-by-category.md).

Jeśli nie musisz dystrybuować biblioteki zawierającej informacje debugowania, użyj opcji [/Zi](z7-zi-zi-debug-information-format.md) zamiast **/Z7** i **/YD**.

Przechowywanie pełnych informacji o debugowaniu w każdym pliku. obj jest niezbędne tylko do dystrybucji bibliotek zawierających informacje o debugowaniu. Spowalnia kompilację i wymaga dużej ilości miejsca na dysku. Gdy **/YC** i **/Z7** są używane bez **/YD**, kompilator przechowuje typowe informacje o debugowaniu w pierwszym pliku. obj utworzonym na podstawie pliku. PCH. Kompilator nie wstawia tych informacji do plików. obj, następnie utworzonych z pliku. PCH; Wstawia odwołania do informacji. Niezależnie od tego, ile plików. obj używa pliku. PCH, tylko jeden plik. obj zawiera typowe informacje o debugowaniu.

Chociaż to domyślne zachowanie powoduje szybsze Kompilowanie i zmniejsza wymagania dotyczące miejsca na dysku, jest to niepożądane, jeśli mała zmiana wymaga ponownego skompilowania pliku. obj zawierającego typowe informacje o debugowaniu. W takim przypadku kompilator musi ponownie skompilować wszystkie pliki obj zawierające odwołania krzyżowe do oryginalnego pliku. obj. Ponadto, jeśli wspólny plik. PCH jest używany przez różne projekty, zależność między odwołaniami do pojedynczego pliku. obj jest trudna.

Aby uzyskać więcej informacji na temat prekompilowanych nagłówków, zobacz:

- [/Y (prekompilowane nagłówki)](y-precompiled-headers.md)

- [Wstępnie skompilowane pliki nagłówkowe](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję kompilatora w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="examples"></a>Przykłady

Załóżmy, że masz dwa pliki podstawowe, F. cpp i G. cpp, z których każda zawiera następujące instrukcje **#include** :

```
#include "windows.h"
#include "etc.h"
```

Następujące polecenie tworzy prekompilowany plik nagłówkowy itp. pch i plik obiektu F. obj:

```
CL /YcETC.H /Z7 F.CPP
```

Plik obiektu F. obj zawiera informacje o typie i symbolach dla systemu WINDOWS. h i itp. h (oraz wszystkie inne pliki nagłówkowe, które zawierają). Teraz można użyć prekompilowanego nagłówka itp. PCH do skompilowania pliku źródłowego G. cpp:

```
CL /YuETC.H /Z7 G.CPP
```

Plik obiektu G. obj nie zawiera informacji o debugowaniu dla prekompilowanego nagłówka, ale po prostu odwołuje się do tych informacji w pliku F. obj. Należy pamiętać, że należy połączyć z plikiem F. obj.

Jeśli prekompilowany nagłówek nie został skompilowany przy użyciu **/Z7**, można nadal używać go w późniejszych kompilacjach przy użyciu **/Z7**. Informacje o debugowaniu są jednak umieszczane w bieżącym pliku obiektu, a symbole lokalne dla funkcji i typów zdefiniowane w prekompilowanym nagłówku nie są dostępne dla debugera.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
