---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1211'
title: Błąd narzędzi konsolidatora LNK1211
ms.date: 12/05/2017
f1_keywords:
- LNK1211
helpviewer_keywords:
- LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
ms.openlocfilehash: d3201055643f5874ccc319f04fb6eb2d976bf67f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341623"
---
# <a name="linker-tools-error-lnk1211"></a>Błąd narzędzi konsolidatora LNK1211

> nie znaleziono wstępnie skompilowanych informacji o typie; *plik "filename*" nie jest połączony ani nadpisany

Plik obiektu *filename* , skompilowany za pomocą [/YC](../../build/reference/yc-create-precompiled-header-file.md), nie został określony w poleceniu linku lub został zastąpiony.

W przypadku tworzenia biblioteki debugowania korzystającej z prekompilowanych nagłówków i określania **/YC** i [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), Visual C++ generuje prekompilowany plik obiektu, który zawiera informacje debugowania. Ten błąd występuje tylko w przypadku przechowywania wstępnie skompilowanego pliku obiektu w bibliotece, używania biblioteki do kompilowania obrazu wykonywalnego, a pliki obiektów, do których istnieją odwołania, nie mają żadnych przechodnich odwołań do żadnej z funkcji, które definiuje wstępnie skompilowany plik obiektu.

Istnieją dwie metody obejścia tej sytuacji:

- Określ opcję kompilatora [/YD](../../build/reference/yd-place-debug-information-in-object-file.md) , aby dodać informacje o debugowaniu z prekompilowanego nagłówka do każdego modułu obiektu. Ta metoda jest mniej pożądana, ponieważ zazwyczaj wytwarza duże moduły obiektów, które mogą zwiększyć czas wymagany do połączenia aplikacji.

- Określ [/yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) i przekaż nazwę dowolnego dowolnego ciągu, podczas tworzenia prekompilowanego pliku nagłówkowego, który nie zawiera żadnych definicji funkcji. Nakazuje kompilatorowi utworzenie symbolu we wstępnie skompilowanym pliku obiektu i wyemituj odwołanie do tego symbolu w każdym pliku obiektu, który użył prekompilowanego pliku nagłówkowego, który jest skojarzony z prekompilowanym plikiem obiektu.

Podczas kompilowania modułu z **/YC** i **/yl**, kompilator tworzy symbol podobny do `__@@_PchSym_@00@...@symbol_name` , gdzie wielokropek (...) reprezentuje ciąg znaków wygenerowany przez kompilator i zapisuje go w module obiektu. Każdy plik źródłowy, który kompilujesz przy użyciu tego prekompilowanego nagłówka, odwołuje się do określonego symbolu, co powoduje, że konsolidator zawiera moduł obiektu i jego informacje debugowania z biblioteki.
