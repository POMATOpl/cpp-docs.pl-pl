---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1277'
title: Błąd narzędzi konsolidatora LNK1277
ms.date: 11/04/2016
f1_keywords:
- LNK1277
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
ms.openlocfilehash: 82a71878d30088bd018c4e54216d53228efe949d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193737"
---
# <a name="linker-tools-error-lnk1277"></a>Błąd narzędzi konsolidatora LNK1277

nie znaleziono rekordu obiektu w pliku PGD (filename)

Podczas używania [/LTCG: PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md)ścieżka jednej z plików Input. lib, def lub. obj różni się od ścieżki, w której zostały znalezione podczas/LTCG: PGINSTRUMENT. Może to być wyjaśnione zmianą w zmiennej środowiskowej LIB po/LTCG: PGINSTRUMENT. Pełna ścieżka do plików wejściowych jest przechowywana w pliku. pgd.

/LTCG: PGOPTIMIZE wymaga, aby dane wejściowe były identyczne z fazą/LTCG: PGINSTRUMENT.

Aby rozwiązać ten problem, wykonaj jedną z następujących czynności:

- Uruchom/LTCG: PGINSTRUMENT, wykonaj ponownie wszystkie uruchomienia testów i Uruchom/LTCG: PGOPTIMIZE.

- Zmień zmienną środowiskową LIB na zainstalowaną w programie/LTCG: PGINSTRUMENT.

Nie zaleca się obejść LNK1277 za pomocą/LTCG: PGUPDATE.
