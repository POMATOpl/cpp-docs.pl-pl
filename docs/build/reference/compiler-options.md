---
description: 'Dowiedz się więcej o: opcje kompilatora'
title: Opcje kompilatora MSVC
ms.date: 12/14/2020
helpviewer_keywords:
- cl.exe compiler
- x86 MSVC compiler
- ARM MSVC compiler
- compiler options, C++
- x64 MSVC compiler
ms.openlocfilehash: f89695b00be4ed67a00f947c6b76943bfa5eaf59
ms.sourcegitcommit: 48b897797b3132ae934b1d191e3870c3c2466335
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2020
ms.locfileid: "97514580"
---
# <a name="compiler-options"></a>Opcje kompilatora

cl.exe jest narzędziem, które kontroluje kompilatory i konsolidatory języka Microsoft C++ (MSVC) C i C++. cl.exe można uruchamiać tylko w systemach operacyjnych, które obsługują Microsoft Visual Studio dla systemu Windows.

> [!NOTE]
> To narzędzie można uruchomić tylko z poziomu wiersza polecenia programu Visual Studio Developer. Nie można uruchomić go z poziomu wiersza polecenia systemu lub Eksploratora plików. Aby uzyskać więcej informacji, zobacz Korzystanie z zestawu [narzędzi MSVC w wierszu polecenia](../building-on-the-command-line.md).

Kompilatory generują pliki (. obj) obiektu Common File Format (COFF). Konsolidator tworzy pliki wykonywalne (exe) lub biblioteki dołączane dynamicznie (dll).

We wszystkich opcjach kompilatora jest rozróżniana wielkość liter. Aby określić opcję kompilatora, można użyć ukośnika ( `/` ) lub kreski ( `-` ).

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
