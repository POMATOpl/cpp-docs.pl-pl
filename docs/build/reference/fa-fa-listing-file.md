---
title: /FA, /Fa (Umieszczanie pliku na liście)
description: Przewodnik referencyjny dotyczący opcji kompilatora Microsoft C++/FA i/FA (lista plików).
ms.date: 11/21/2020
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AssemblerListingLocation
- VC.Project.VCCLCompilerTool.ConfigureASMListing
- VC.Project.VCCLWCECompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.AssemblerListingLocation
- /fa
- VC.Project.VCCLCompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
helpviewer_keywords:
- FA compiler option [C++]
- /FA compiler option [C++]
- -FA compiler option [C++]
- listing file type
- assembly-only listing
ms.openlocfilehash: 7e8e39fea55bb69eaa0ae914eeabcafef4ac7849
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440232"
---
# <a name="fa-fa-listing-file"></a>`/FA`, `/Fa` (Lista plików)

Tworzy plik listy zawierający kod asemblera.

## <a name="syntax"></a>Składnia

> **`/FA`**[**`c`**\][**`s`**\][**`u`**]\
> **`/Fa`**_ścieżki_

## <a name="remarks"></a>Uwagi

**`/FA`** Opcja kompilatora generuje plik listy asemblera dla każdej jednostki tłumaczenia w kompilacji, która zwykle odnosi się do pliku źródłowego C lub C++. Domyślnie tylko asembler jest zawarty w pliku listy, który jest kodowany jako ANSI. Opcjonalne **`c`** argumenty, **`s`** i **`u`** do **`/FA`** kontrolowania, czy kod komputera lub kod źródłowy są wyprowadzane razem z listą asemblera i czy lista jest zakodowana jako UTF-8.

Domyślnie każdy plik listy otrzymuje taką samą nazwę bazową jak plik źródłowy i ma *`.asm`* rozszerzenie. Gdy kod komputera jest uwzględniany przy użyciu **`c`** opcji, plik listy ma *`.cod`* rozszerzenie. Można zmienić nazwę i rozszerzenie pliku listy oraz katalog, w którym została utworzona przy użyciu **`/Fa`** opcji.

### <a name="fa-arguments"></a>`/FA` argumentu

dawaj
Na liście znajduje się tylko język asemblera.

**`c`**\
Opcjonalny. Zawiera kod maszyny na liście.

**`s`**\
Opcjonalny. Zawiera kod źródłowy znajdujący się na liście.

**`u`**\
Opcjonalny. Koduje plik listy w formacie UTF-8 i zawiera znacznik kolejności bajtów. Domyślnie plik jest zakodowany jako ANSI. Użyj polecenia **`u`** , aby utworzyć plik listy, który jest wyświetlany poprawnie w dowolnym systemie, lub jeśli używasz plików kodu źródłowego Unicode jako danych wejściowych kompilatora.

Jeśli obie **`s`** i **`u`** są określone, a jeśli plik kodu źródłowego używa kodowania Unicode innego niż UTF-8, wówczas wiersze kodu w *`.asm`* pliku mogą nie być wyświetlane poprawnie.

### <a name="fa-argument"></a>Argument `/Fa`

dawaj
Jeden *źródłowy plik ASM* jest tworzony dla każdego pliku kodu źródłowego w kompilacji.

*Nazwa pliku*\
Kompilator umieszcza plik z listą o nazwie *filename*. asm w bieżącym katalogu. Ten formularz argumentu jest prawidłowy tylko podczas kompilowania pojedynczego pliku kodu źródłowego.

*filename. Extension*\
Kompilator umieszcza plik z listą o nazwie *filename. Extension* w bieżącym katalogu. Ten formularz argumentu jest prawidłowy tylko podczas kompilowania pojedynczego pliku kodu źródłowego.

*katalogi*__\\__\
Kompilator tworzy jeden plik *source_file. asm* dla każdego pliku kodu źródłowego w kompilacji. Znajduje się w określonym *katalogu*. Wymagany jest końcowy ukośnik odwrotny. Dozwolone są tylko ścieżki na bieżącym dysku.

*katalog* __\\__ *Nazwa pliku*\
Plik z listą o nazwie *filename. asm* jest umieszczony w określonym *katalogu*. Ten formularz argumentu jest prawidłowy tylko podczas kompilowania pojedynczego pliku kodu źródłowego.

*katalog* __\\__ *filename. Extension*\
Plik z listą o nazwie *filename. Extension* został umieszczony w określonym *katalogu*. Ten formularz argumentu jest prawidłowy tylko podczas kompilowania pojedynczego pliku kodu źródłowego.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz **Configuration Properties**  >  stronę właściwości pliki wyjściowe **C/C++** właściwości konfiguracji  >  **Output Files** .

1. Zmodyfikuj właściwość **danych wyjściowych asemblera** , aby ustawić opcje **/FAc** i **/FAS** dla asemblera, komputera i kodu źródłowego. Aby ustawić opcję dla danych wyjściowych ANSI lub UTF-8, zmodyfikuj wartość w polu **Użyj Unicode dla programu asemblera** **`/FAu`** . Zmodyfikuj **lokalizację listy ASM** , aby ustawić **`/Fa`** opcję wyświetlania nazwy pliku i lokalizacji.

Ustawienie **danych wyjściowych asemblera** i **użycie Unicode dla właściwości list asemblera** może spowodować [Ostrzeżenie wiersza polecenia D9025](../../error-messages/tool-errors/command-line-warning-d9025.md). Aby połączyć te opcje w IDE, w zamian użyj pola **dodatkowe opcje** na stronie właściwości **wiersza polecenia** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A> lub <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A> . Aby określić **/FAU**, zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> .

## <a name="example"></a>Przykład

Poniższy wiersz polecenia generuje listę połączonych źródeł i kodu maszynowego o nazwie *`HELLO.cod`* :

```cmd
CL /FAcs HELLO.CPP
```

## <a name="see-also"></a>Zobacz też

[Opcje pliku wyjściowego (/F)](output-file-f-options.md)\
[Opcje kompilatora MSVC](compiler-options.md)\
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)\
[Określanie nazwy ścieżki](specifying-the-pathname.md)
