---
description: Dowiedz się więcej na temat:/c (Kompiluj bez konsolidacji)
title: /c (Kompiluj bez konsolidacji)
ms.date: 11/04/2016
f1_keywords:
- /c
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
ms.openlocfilehash: b9dd692dd99cddf63015fe26e37dc54841816f7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179372"
---
# <a name="c-compile-without-linking"></a>/c (Kompiluj bez konsolidacji)

Zapobiega automatycznemu wywołaniu LINKu.

## <a name="syntax"></a>Składnia

```
/c
```

## <a name="remarks"></a>Uwagi

Kompilowanie przy użyciu **/c** powoduje utworzenie tylko plików. obj. Musisz wywołać LINK jawnie z odpowiednimi plikami i opcjami, aby wykonać fazę konsolidacji kompilacji.

Każdy projekt wewnętrzny utworzony w środowisku programistycznym domyślnie używa **/c** opcji.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

- Ta opcja jest niedostępna w środowisku deweloperskim.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Aby programowo ustawić tę opcję kompilatora, zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A> .

## <a name="example"></a>Przykład

Poniższy wiersz polecenia tworzy pliki obiektów FIRST. obj i SECOND. obj. TRZECI. obj jest ignorowany.

```
CL /c FIRST.C SECOND.C THIRD.OBJ
```

Aby utworzyć plik wykonywalny, należy wywołać LINK:

```
LINK firsti.obj second.obj third.obj /OUT:filename.exe
```

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
