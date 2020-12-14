---
description: Dowiedz się więcej o:/LN (Utwórz moduł MSIL)
title: /LN (Utwórz moduł MSIL)
ms.date: 11/04/2016
f1_keywords:
- /LN
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
ms.openlocfilehash: 63b6f47fe6bef24341d3c19a6ad96ac3808e486e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190924"
---
# <a name="ln-create-msil-module"></a>/LN (Utwórz moduł MSIL)

Określa, że nie należy wstawiać manifestu zestawu do pliku wyjściowego.

## <a name="syntax"></a>Składnia

```
/LN
```

## <a name="remarks"></a>Uwagi

Domyślnie **/LN** nie jest w efekcie (manifest zestawu jest wstawiany do pliku wyjściowego).

Gdy **/LN** jest używany, należy również użyć jednej z opcji [/CLR (kompilacja języka CLR)](clr-common-language-runtime-compilation.md) .

Program zarządzany, który nie ma metadanych zestawu, jest nazywany modułem. Jeśli kompilujesz za pomocą [/c (Kompiluj bez konsolidacji)](c-compile-without-linking.md) i **/LN**, określ [/NOASSEMBLY (Utwórz moduł MSIL)](noassembly-create-a-msil-module.md) w fazie konsolidatora, aby utworzyć plik wyjściowy.

Możesz chcieć utworzyć moduły, jeśli chcesz użyć podejścia opartego na składniku do kompilowania zestawów.  Oznacza to, że można tworzyć typy i kompilować je do modułów.  Następnie można wygenerować zestaw z co najmniej jednego modułu.  Aby uzyskać więcej informacji na temat tworzenia zestawów z modułów, zobacz [. moduły plików jako dane wejściowe konsolidatora](netmodule-files-as-linker-input.md) lub [Al.exe (Konsolidator zestawu)](/dotnet/framework/tools/al-exe-assembly-linker).

Domyślnym rozszerzeniem pliku modułu jest. module.

W wersjach przed programem Visual Studio 2005 moduł został utworzony z **opcją/CLR: noAssembly**.

MSVC konsolidator akceptuje pliki. module jako dane wejściowe i plik wyjściowy utworzony przez konsolidator będzie zestawem lub modułem, który nie jest zależny od czasu wykonywania w żadnym z modułów.  Aby uzyskać więcej informacji, zobacz [. moduły plików jako dane wejściowe konsolidatora](netmodule-files-as-linker-input.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

- Określ [/NOASSEMBLY (Utwórz moduł MSIL)](noassembly-create-a-msil-module.md) w fazie konsolidatora, aby utworzyć plik wyjściowy.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Nie można programowo zmienić tej opcji kompilatora.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
