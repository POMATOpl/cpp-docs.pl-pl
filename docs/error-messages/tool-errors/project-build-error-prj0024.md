---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0024'
title: Błąd PRJ0024 kompilacji projektu
ms.date: 08/27/2018
f1_keywords:
- PRJ0024
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
ms.openlocfilehash: e42df62181d02cf8d4696cc4f48afcec52cd4d76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150465"
---
# <a name="project-build-error-prj0024"></a>Błąd PRJ0024 kompilacji projektu

> Nie można przetłumaczyć ścieżki Unicode "*Path*" na stronę kodową ANSI użytkownika.

*ścieżka* to oryginalna wersja Unicode ciągu ścieżki. Ten błąd może wystąpić w przypadkach, gdy istnieje ścieżka Unicode, której nie można bezpośrednio przetłumaczyć na ANSI na bieżącą stronę kodową systemu.

Ten błąd może wystąpić, jeśli pracujesz z projektem, który został opracowany w systemie przy użyciu strony kodowej, która nie znajduje się na komputerze.

Rozwiązaniem tego błędu jest zaktualizowanie ścieżki w celu użycia tekstu ANSI lub zainstalowanie strony kodowej na komputerze i ustawienie jej jako wartości domyślnej systemu.
