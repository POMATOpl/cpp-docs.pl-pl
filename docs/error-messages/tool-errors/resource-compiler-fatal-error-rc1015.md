---
description: 'Dowiedz się więcej na temat: błąd krytyczny kompilatora zasobów kompilatora zasobów RC1015'
title: Błąd krytyczny kompilatora zasobów RC1015
ms.date: 11/04/2016
f1_keywords:
- RC1015
helpviewer_keywords:
- RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
ms.openlocfilehash: 41afe385189d35e80e5f624d379b45c0dca17441
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265665"
---
# <a name="resource-compiler-fatal-error-rc1015"></a>Błąd krytyczny kompilatora zasobów RC1015

nie można otworzyć pliku dołączanego "filename"

Podany plik dyrektywy include nie istnieje, nie można go otworzyć lub nie został odnaleziony.

Upewnij się, że ustawienia środowiska są prawidłowe i że określono poprawną ścieżkę do pliku. Upewnij się, że w kompilatorze zasobów są dostępne wystarczające dojścia do plików. Jeśli plik znajduje się na dysku sieciowym, upewnij się, że masz uprawnienia do otwierania tego pliku.

KOMPILATORA zasobów RC1015 może wystąpić nawet wtedy, gdy plik dołączany istnieje w katalogu określonym jako dodatkowy katalog dołączania we właściwościach konfiguracji — > zasoby — > stronie właściwości ogólne. Określ pełną ścieżkę do pliku dołączanego.
