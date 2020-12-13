---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1307'
title: Błąd krytyczny C1307
ms.date: 11/04/2016
f1_keywords:
- C1307
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
ms.openlocfilehash: 235d51f272669ba3b205eea5c3703b40dc1e9077
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177890"
---
# <a name="fatal-error-c1307"></a>Błąd krytyczny C1307

Program został wyedytowany od czasu zebrania danych profilowych

W przypadku korzystania z [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)konsolidator wykrył Moduł wejściowy, który został ponownie skompilowany po/LTCG: PGINSTRUMENT i że moduł został zmieniony do punktu, w którym istniejące dane profilowe nie są już ważne. Na przykład, jeśli wykres wywołań został zmieniony w module rekompilowanym, kompilator wygeneruje C1307.

Aby rozwiązać ten problem, Uruchom/LTCG: PGINSTRUMENT, ponów wszystkie przebiegi testowe i Uruchom/LTCG: PGOPTIMIZE. Jeśli nie możesz uruchomić/LTCG: PGINSTRUMENT i wykonaj ponownie wszystkie przebiegi testowe, użyj/LTCG: PGUPDATE zamiast/LTCG: PGOPTIMIZE w celu utworzenia zoptymalizowanego obrazu.
