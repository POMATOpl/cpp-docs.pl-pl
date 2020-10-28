---
title: /clr (Kompilacja środowiska uruchomieniowego języka wspólnego)
description: Użyj opcji kompilatora Microsoft C++ Option/CLR, aby skompilować kod C++/CLI i C++ jako kod zarządzany.
ms.date: 10/27/2020
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
ms.openlocfilehash: 9d27d9fb6226f84c4ea67a8f9387a595ba65468b
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907600"
---
# <a name="clr-common-language-runtime-compilation"></a>`/clr` (Kompilacja środowiska uruchomieniowego języka wspólnego)

Umożliwia aplikacjom i składnikom korzystanie z funkcji środowiska uruchomieniowego języka wspólnego (CLR) i umożliwia kompilację C++/CLI.

## <a name="syntax"></a>Składnia

> **`/clr`**\[**`:`**_Opcje_ ]

## <a name="arguments"></a>Argumenty

*Opcje*\
Co najmniej jeden z następujących argumentów oddzielonych przecinkami.

- brak

   Bez opcji program **`/clr`** tworzy metadane dla składnika. Metadane mogą być używane przez inne aplikacje CLR i umożliwiają składnikowi korzystanie z typów i danych w metadanych innych składników CLR. Aby uzyskać więcej informacji, zobacz [zestawy mieszane (natywne i zarządzane)](../../dotnet/mixed-native-and-managed-assemblies.md).

- **`NetCore`**

   **`/clr:NetCore`** Tworzy metadane i kod dla składnika przy użyciu najnowszego międzyplatformowego programu .NET Framework, znanego również jako .NET Core. Metadane mogą być używane przez inne aplikacje platformy .NET Core. Ponadto opcja umożliwia składnikowi korzystanie z typów i danych w metadanych innych składników .NET Core.

- **`nostdlib`**

   Nakazuje kompilatorowi ignorowanie domyślnego *`\clr`* katalogu. Kompilator tworzy błędy, jeśli dołączysz wiele wersji biblioteki DLL, takich jak System.dll. Ta opcja umożliwia określenie konkretnej platformy do użycia podczas kompilacji.

- **`pure`**

   **`/clr:pure` jest przestarzały** . Opcja zostanie usunięta w programie Visual Studio 2017 i nowszych. Zalecamy, aby kod portu, który musi być czystym MSIL do języka C#.

- **`safe`**

   **`/clr:safe` jest przestarzały** . Opcja zostanie usunięta w programie Visual Studio 2017 i nowszych. Zalecamy, aby kod portu, który musi być bezpiecznym MSIL do języka C#.

- **`noAssembly`**

   **`/clr:noAssembly` jest przestarzały** . Zamiast tego użyj [ `/LN` (Utwórz moduł MSIL)](ln-create-msil-module.md) .

   Instruuje kompilator, aby nie wstawiał manifestu zestawu do pliku wyjściowego. Domyślnie **`noAssembly`** opcja nie jest włączona.

   Program zarządzany, który nie ma metadanych zestawu, jest znany jako *moduł* . **`noAssembly`** Opcja może być używana tylko do tworzenia modułu. Jeśli kompilujesz za pomocą [`/c`](c-compile-without-linking.md) i **`/clr:noAssembly`** , wskaż [`/NOASSEMBLY`](noassembly-create-a-msil-module.md) opcję w fazie konsolidatora, aby utworzyć moduł.

   Wymagany jest program Visual Studio **`/clr:noAssembly`** 2005 **`/LD`** . **`/LD`** jest teraz implikowane po określeniu **`/clr:noAssembly`** .

- **`initialAppDomain`**

   **`initialAppDomain` jest przestarzały** . Umożliwia uruchamianie aplikacji C++/CLI w wersji 1 środowiska CLR.  Aplikacja, która jest skompilowana przy użyciu, **`initialAppDomain`** nie powinna być używana przez aplikację, która używa ASP.NET, ponieważ nie jest obsługiwana w wersji 1 środowiska CLR.

## <a name="remarks"></a>Uwagi

*Kod zarządzany* to kod, który może być sprawdzany i zarządzany przez środowisko CLR. Kod zarządzany może uzyskiwać dostęp do obiektów zarządzanych. Aby uzyskać więcej informacji, zobacz [ `/clr` ograniczenia](clr-restrictions.md).

Aby uzyskać informacje o sposobie tworzenia aplikacji, które definiują i zużywają typy zarządzane w języku C++, zobacz [rozszerzenia składników dla platform środowiska uruchomieniowego](../../extensions/component-extensions-for-runtime-platforms.md).

Aplikacja skompilowana przy użyciu programu **`/clr`** może lub nie może zawierać danych zarządzanych.

Aby włączyć debugowanie dla aplikacji zarządzanej, zobacz [ `/ASSEMBLYDEBUG` (Add DebuggableAttribute)](assemblydebug-add-debuggableattribute.md).

Tylko typy CLR są tworzone na stertie zebranych elementów bezużytecznych. Aby uzyskać więcej informacji, zobacz [klasy i struktury](../../extensions/classes-and-structs-cpp-component-extensions.md). Aby skompilować funkcję do kodu natywnego, użyj `unmanaged` dyrektywy pragma. Aby uzyskać więcej informacji, [ `managed` Zobacz `unmanaged` . ](../../preprocessor/managed-unmanaged.md)

Domyślnie, **`/clr`** nie obowiązuje. Gdy **`/clr`** jest włączona, **`/MD`** również działa. Aby uzyskać więcej informacji, zobacz [ `/MD` , `/MT` , `/LD` (Użyj biblioteki Run-Time)](md-mt-ld-use-run-time-library.md). **`/MD`** zapewnia, że dynamicznie połączone i wielowątkowe wersje procedur środowiska uruchomieniowego są wybierane ze standardowych plików nagłówkowych. Wielowątkowość jest wymagana do zarządzanego programowania, ponieważ moduł wyrzucania elementów bezużytecznych CLR uruchamia finalizatory w wątku pomocniczym.

Jeśli kompilujesz przy użyciu **`/c`** , możesz określić typ CLR wynikowego pliku wyjściowego przy użyciu [`/CLRIMAGETYPE`](clrimagetype-specify-type-of-clr-image.md) opcji konsolidatora.

**`/clr`** oznacza **`/EHa`** , **`/EH`** że dla programu nie są obsługiwane żadne inne opcje **`/clr`** . Aby uzyskać więcej informacji, zobacz [ `/EH` (model obsługi wyjątków)](eh-exception-handling-model.md).

Aby uzyskać informacje na temat sposobu określania typu obrazu CLR dla pliku, zobacz [`/CLRHEADER`](clrheader.md) .

Wszystkie moduły przekazane do danego wywołania konsolidatora muszą zostać skompilowane przy użyciu tej samej opcji kompilatora środowiska uruchomieniowego ( **`/MD`** lub **`/LD`** ).

Użyj [`/ASSEMBLYRESOURCE`](assemblyresource-embed-a-managed-resource.md) opcji konsolidatora, aby osadzić zasób w zestawie. [`/DELAYSIGN`](delaysign-partially-sign-an-assembly.md), [`/KEYCONTAINER`](keycontainer-specify-a-key-container-to-sign-an-assembly.md) i [`/KEYFILE`](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) Opcje konsolidatora umożliwiają również dostosowywanie sposobu tworzenia zestawu.

Gdy **`/clr`** jest używany, `_MANAGED` symbol jest zdefiniowany jako 1. Aby uzyskać więcej informacji, zobacz [wstępnie zdefiniowane makra](../../preprocessor/predefined-macros.md).

Zmienne globalne w pliku obiektu natywnego są inicjowane jako pierwsze (podczas `DllMain` gdy plik wykonywalny jest biblioteką DLL), a następnie zmienne globalne w sekcji zarządzanej są inicjowane (przed uruchomieniem dowolnego kodu zarządzanego). [`#pragma init_seg`](../../preprocessor/init-seg.md) dotyczy tylko kolejności inicjowania w kategorii zarządzane i niezarządzane.

### <a name="metadata-and-unnamed-classes"></a>Metadane i nienazwane klasy

Nienazwane klasy są wyświetlane w metadanych pod nazwami, takimi jak  `$UnnamedClass$<crc-of-current-file-name>$<index>$` , gdzie `<index>` jest sekwencyjną liczbą klas nienazwanych w kompilacji. Na przykład poniższy kod przykład generuje nienazwaną klasę w metadanych.

```cpp
// clr_unnamed_class.cpp
// compile by using: /clr /LD
class {} x;
```

Użyj ildasm.exe, aby wyświetlić metadane.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Ustaw listę rozwijaną **Konfiguracja** na **wszystkie konfiguracje** i Ustaw listę rozwijaną **platformy** na **wszystkie platformy** .

1. Wybierz stronę **Ogólne właściwości konfiguracji**  >  **C/C++**  >  **General** .

1. Zmodyfikuj właściwość **Obsługa środowiska uruchomieniowego** CLR. Wybierz **przycisk OK** , aby zapisać zmiany.

> [!NOTE]
> W środowisku IDE programu Visual Studio **`/clr`** opcję kompilatora można ustawić indywidualnie na stronie Ogólne **Właściwości konfiguracji**  >  **C/C++**  >  **General** okna dialogowego strony właściwości. Zalecamy jednak użycie szablonu CLR do utworzenia projektu. Ustawia wszystkie właściwości wymagane do pomyślnego utworzenia składnika CLR. Innym sposobem ustawienia tych właściwości jest użycie właściwości **Obsługa środowiska uruchomieniowego** CLR na stronie Zaawansowane **Właściwości konfiguracji** w  >  **Advanced** oknie dialogowym strony właściwości. Ta właściwość ustawia wszystkie inne opcje narzędzi związanych ze środowiskiem CLR jednocześnie.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAsManaged>.

## <a name="see-also"></a>Zobacz także

[Opcje kompilatora MSVC](compiler-options.md)\
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
