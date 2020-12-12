---
description: 'Dowiedz się więcej o: opcje kompilatora'
title: Opcje kompilatora MSVC
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler
- x86 MSVC compiler
- ARM MSVC compiler
- compiler options, C++
- x64 MSVC compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
ms.openlocfilehash: a6b124fa5fce68844d53c1324da48c17ef5a9ccf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197026"
---
# <a name="compiler-options"></a>Opcje kompilatora

cl.exe jest narzędziem, które kontroluje kompilatory i konsolidatory języka Microsoft C++ (MSVC) C i C++. cl.exe można uruchamiać tylko w systemach operacyjnych, które obsługują Microsoft Visual Studio dla systemu Windows.

> [!NOTE]
> To narzędzie można uruchomić tylko z poziomu wiersza polecenia programu Visual Studio Developer. Nie można uruchomić go z poziomu wiersza polecenia systemu lub Eksploratora plików. Aby uzyskać więcej informacji, zobacz Korzystanie z zestawu [narzędzi MSVC w wierszu polecenia](../building-on-the-command-line.md).

Kompilatory generują pliki (. obj) obiektu Common File Format (COFF). Konsolidator tworzy pliki wykonywalne (exe) lub biblioteki dołączane dynamicznie (dll).

Należy pamiętać, że w przypadku wszystkich opcji kompilatora jest uwzględniana wielkość liter. Aby określić opcję kompilatora, można użyć ukośnika ( `/` ) lub kreski ( `-` ).

Aby skompilować bez konsolidacji, użyj [/c](c-compile-without-linking.md) opcji.

## <a name="find-a-compiler-option"></a>Znajdź opcję kompilatora

Aby znaleźć określoną opcję kompilatora, zobacz jedną z następujących list:

- [Opcje kompilatora w porządku alfabetycznym](compiler-options-listed-alphabetically.md)

- [Opcje kompilatora na liście według kategorii](compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>Określ opcje kompilatora

W temacie dla każdej opcji kompilatora omówiono, jak można ją ustawić w środowisku programistycznym. Aby uzyskać informacje na temat określania opcji poza środowiskiem programistycznym, zobacz:

- [Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)

- [Pliki poleceń CL](cl-command-files.md)

- [Zmienne środowiskowe CL](cl-environment-variables.md)

## <a name="related-build-tools"></a>Powiązane narzędzia do kompilacji

[Opcje konsolidatora MSVC](linker-options.md) mają również wpływ na sposób kompilowania programu.

## <a name="see-also"></a>Zobacz też

[Odwołanie kompilacji C/C++](c-cpp-building-reference.md)<br/>
[CL wywołuje konsolidator](cl-invokes-the-linker.md)
