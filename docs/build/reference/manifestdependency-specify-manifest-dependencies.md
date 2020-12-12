---
description: Dowiedz się więcej o:/MANIFESTDEPENDENCY (Określ zależności manifestu)
title: /MANIFESTDEPENDENCY (Określ zależności manifestu)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalManifestDependencies
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
ms.openlocfilehash: 129dc84818b0bda9b2106c0d07dca5b605dc6f96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199170"
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (Określ zależności manifestu)

```
/MANIFESTDEPENDENCY:manifest_dependency
```

## <a name="remarks"></a>Uwagi

/MANIFESTDEPENDENCY umożliwia określenie atrybutów, które zostaną umieszczone w \<dependency> sekcji pliku manifestu.

Aby uzyskać informacje na temat sposobu tworzenia pliku manifestu, zobacz [/manifest (Tworzenie manifestu zestawu side-by-Side)](manifest-create-side-by-side-assembly-manifest.md) .

Aby uzyskać więcej informacji na temat \<dependency> sekcji pliku manifestu, zobacz [pliki konfiguracji wydawcy](/windows/win32/SbsCs/publisher-configuration-files).

Informacje/MANIFESTDEPENDENCY można przesłać do konsolidatora na jeden z dwóch sposobów:

- Bezpośrednio w wierszu polecenia (lub w pliku odpowiedzi) z/MANIFESTDEPENDENCY.

- Za pomocą dyrektywy pragma [komentarza](../../preprocessor/comment-c-cpp.md) .

Poniższy przykład pokazuje komentarz/MANIFESTDEPENDENCY przekazana za pośrednictwem dyrektywy pragma.

```cpp
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")
```

co spowoduje, że w pliku manifestu zostanie umieszczony następujący wpis:

```xml
<dependency>
  <dependentAssembly>
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />
  </dependentAssembly>
</dependency>
```

Te same Komentarze/MANIFESTDEPENDENCY można przesłać w wierszu polecenia w następujący sposób:

```cmd
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"
```

Konsolidator będzie zbierać Komentarze/MANIFESTDEPENDENCY, eliminować zduplikowane wpisy, a następnie dodać otrzymany ciąg XML do pliku manifestu.  Jeśli konsolidator znajdzie wpisy powodujące konflikt, plik manifestu zostanie uszkodzony i aplikacja nie zostanie uruchomiona (można dodać wpis do dziennika zdarzeń, wskazując Źródło błędu).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz pozycję **Właściwości konfiguracji**  >    >  Strona właściwości **pliku manifestu** konsolidatora.

1. Zmodyfikuj **dodatkową właściwość zależności manifestu** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
