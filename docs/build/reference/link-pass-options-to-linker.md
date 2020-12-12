---
description: Dowiedz się więcej na temat:/Link (Przekaż opcje do konsolidatora)
title: /link (Przepuść opcje do konsolidatora)
ms.date: 03/25/2019
f1_keywords:
- /link
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
ms.openlocfilehash: 3617a005e6adbc41a589606aa145712fa2df442d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199496"
---
# <a name="link-pass-options-to-linker"></a>/link (Przepuść opcje do konsolidatora)

Przekazuje jedną lub więcej opcji konsolidatora do konsolidatora.

## <a name="syntax"></a>Składnia

> **/link** *— Opcje konsolidatora*

## <a name="arguments"></a>Argumenty

*Opcje konsolidatora*<br/>
Opcja konsolidatora lub opcje, które mają zostać przesłane do konsolidatora.

## <a name="remarks"></a>Uwagi

Opcja **/link** i jej Opcje konsolidatora muszą występować po dowolnych nazwach plików i opcjach CL. Między **/link** i wszystkimi opcjami konsolidatora jest wymagana spacja. Aby uzyskać więcej informacji, zobacz [MSVC konsolidator Reference](linking.md).

## <a name="example"></a>Przykład

Ten przykładowy wiersz polecenia kompiluje *Witaj. cpp* i łączy go z istniejącym plikiem obiektu *. obj*. Następnie przekazuje dodatkowe polecenie **/Version** do konsolidatora:

`cl /W4 /EHsc hello.cpp there.obj /link /VERSION:3.14`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

IDE zwykle wysyła osobne polecenia do kompilowania i łączenia kodu. Opcje konsolidatora można ustawić na stronach właściwości projektu.

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder   >  **konsolidatora** właściwości konfiguracji.

1. Zmodyfikuj jedną lub więcej właściwości. Wybierz **przycisk OK** , aby zapisać zmiany.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Nie można programowo zmienić tej opcji kompilatora.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
