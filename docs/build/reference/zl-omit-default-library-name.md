---
description: Dowiedz się więcej o:/zl (Pomiń domyślną nazwę biblioteki)
title: /Zl (Pomiń domyślną nazwę biblioteki)
ms.date: 11/04/2016
f1_keywords:
- /zl
- VC.Project.VCCLCompilerTool.OmitDefaultLibName
helpviewer_keywords:
- -Zl compiler option [C++]
- ZI compiler option
- Omit Default Library Name compiler option
- /Zl compiler option [C++]
- default libraries, omitting names
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
ms.openlocfilehash: eaf39b7bfe1a2b7f2d2c7754cccf8061543e4c7c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224429"
---
# <a name="zl-omit-default-library-name"></a>/Zl (Pomiń domyślną nazwę biblioteki)

Pomija domyślną nazwę biblioteki środowiska uruchomieniowego C z pliku. obj. Domyślnie kompilator umieszcza nazwę biblioteki w pliku. obj, aby skierować konsolidator do odpowiedniej biblioteki.

## <a name="syntax"></a>Składnia

```
/Zl
```

## <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat biblioteki domyślnej, zobacz [Korzystanie z biblioteki Run-Time](md-mt-ld-use-run-time-library.md).

Za pomocą **/zl** można kompilować pliki. obj, które planujesz umieścić w bibliotece. Mimo że pominięcie nazwy biblioteki powoduje zaoszczędzenie tylko niewielkiej ilości miejsca dla pojedynczego pliku. obj, zapisana przestrzeń jest istotna w bibliotece zawierającej wiele modułów obiektów.

Ta opcja jest opcją zaawansowaną. Ustawienie tej opcji spowoduje usunięcie pewnej obsługi biblioteki środowiska uruchomieniowego C, która może być wymagana przez aplikację, co spowoduje błędy w czasie połączenia, jeśli aplikacja zależy od tej obsługi. W przypadku korzystania z tej opcji należy udostępnić wymagane składniki w inny sposób.

Użyj [/NODEFAULTLIB (Ignoruj biblioteki)](nodefaultlib-ignore-libraries.md). Aby skierować konsolidator do ignorowania odwołań do bibliotek we wszystkich plikach. obj.

Aby uzyskać więcej informacji, zobacz [funkcje biblioteki CRT](../../c-runtime-library/crt-library-features.md).

Podczas kompilowania z **/zl**, `_VC_NODEFAULTLIB` jest zdefiniowany.  Na przykład:

```cpp
// vc_nodefaultlib.cpp
// compile with: /Zl
void Test() {
   #ifdef _VC_NODEFAULTLIB
      int i;
   #endif

   int i;   // C2086
}
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **Zaawansowane** .

1. Zmodyfikuj właściwość **pomijanie domyślnych nazw bibliotek** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
