---
description: Dowiedz się więcej na temat:/FD (minimalna ponowna kompilacja IDE)
title: /FD (Minimalna ponowna kompilacja IDE)
ms.date: 04/08/2019
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: d9b2a91c14b80890c703b8f4dd5b2de3aefb012b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192294"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (Minimalna ponowna kompilacja IDE)

**/FD** jest uwidaczniana tylko użytkownikom na stronie właściwości [wiersza polecenia](command-line-property-pages.md) okna dialogowego **strony właściwości** projektu C++. Jest ona dostępna, jeśli i tylko wtedy, gdy opcja nie jest zaznaczona i wyłączona [(Włącz minimalną](gm-enable-minimal-rebuild.md) ponowną kompilację). **/FD** nie jest efektem innym niż środowisko programistyczne. **/FD** nie jest ujawniane w danych wyjściowych `cl /?` .

Jeśli nie włączysz opcji **/GM** przestarzałe w środowisku deweloperskim, zostanie użyta wartość **/FD** . **/FD** gwarantuje, że plik. IDB ma wystarczające informacje o zależnościach. **/FD** jest używana tylko przez środowisko programistyczne i nie należy go używać z wiersza polecenia ani skryptu kompilacji.

## <a name="see-also"></a>Zobacz też

[Opcje pliku wyjściowego (/F)](output-file-f-options.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
