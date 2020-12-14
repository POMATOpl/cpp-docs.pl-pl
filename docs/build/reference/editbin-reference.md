---
description: 'Dowiedz się więcej o: polecenia EDITBIN Reference'
title: Odwołanie EDITBIN
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
ms.openlocfilehash: ad211ab85ac00cd716b7c3b8e381a9a448ea04ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201030"
---
# <a name="editbin-reference"></a>Odwołanie EDITBIN

Edytor plików binarnych Microsoft COFF (EDITBIN.EXE) modyfikuje pliki binarne Common Object Format (COFF). Można użyć polecenia EDITBIN do modyfikacji plików obiektów, plików wykonywalnych i bibliotek dołączanych dynamicznie (DLL).

> [!NOTE]
> To narzędzie można uruchomić tylko z poziomu wiersza polecenia programu Visual Studio. Nie można uruchomić go z poziomu wiersza polecenia systemu lub Eksploratora plików.

POLECENIA EDITBIN nie jest dostępny do użytku dla plików utworzonych przy użyciu opcji kompilatora [/GL](gl-whole-program-optimization.md) . Wszelkie modyfikacje plików binarnych utworzonych za pomocą/GL będą musiały zostać osiągnięte przez ponowną kompilację i konsolidację.

- [Wiersz polecenia EDITBIN](editbin-command-line.md)

- [Opcje EDITBIN](editbin-options.md)

## <a name="see-also"></a>Zobacz też

[Dodatkowe narzędzia do kompilacji MSVC](c-cpp-build-tools.md)
