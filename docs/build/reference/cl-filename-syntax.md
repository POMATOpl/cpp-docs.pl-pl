---
description: Dowiedz się więcej o składni nazwy pliku CL
title: Składnia nazwy pliku CL
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
ms.openlocfilehash: c7a657b54f69e2cdc0a126c55bb4102589a84290
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182445"
---
# <a name="cl-filename-syntax"></a>Składnia nazwy pliku CL

CL akceptuje pliki o nazwach zgodnych z konwencjami nazewnictwa FAT, HPFS lub NTFS. Każda nazwa pliku może zawierać pełną lub częściową ścieżkę. Pełna ścieżka zawiera nazwę dysku i jedną lub więcej nazw katalogów. CL akceptuje nazwy plików rozdzielone ukośnikami ( \\ ) lub ukośnikami (/). Nazwy plików zawierające spacje muszą być ujęte w znaki podwójnego cudzysłowu. Ścieżka częściowa pomija nazwę dysku, który CL przyjmuje jako bieżący dysk. Jeśli ścieżka nie zostanie określona, CL przyjmie, że plik znajduje się w bieżącym katalogu.

Rozszerzenie nazwy pliku określa sposób przetwarzania plików. Pliki c i C++, które mają rozszerzenie. C,. cxx lub. cpp, są kompilowane. Inne pliki, w tym pliki obj, biblioteki (. lib) i pliki definicji modułów (. def), są przesyłane do konsolidatora bez przetwarzania.

## <a name="see-also"></a>Zobacz też

[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
