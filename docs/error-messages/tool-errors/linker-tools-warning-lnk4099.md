---
description: 'Dowiedz się więcej o: LNK4099 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4099 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4099
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
ms.openlocfilehash: 1e063cce9c884b8952e4bd5807b0d4a7683d4d54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133773"
---
# <a name="linker-tools-warning-lnk4099"></a>Ostrzeżenie LNK4099 narzędzi konsolidatora

Nie znaleziono pliku PDB "filename" z elementem "Object/Library" lub "Path"; Łączenie obiektu bez informacji debugowania

Konsolidator nie może odnaleźć pliku. pdb. Skopiuj go do katalogu, który zawiera `object/library` .

Aby znaleźć nazwę pliku. pdb skojarzonego z plikiem obiektu:

1. Wyodrębnij plik obiektu z biblioteki przy użyciu [lib](../../build/reference/lib-reference.md) **/Extract:** `objectname` **. obj** `xyz` **. lib**.

1. Sprawdź ścieżkę do pliku. pdb z **polecenia DUMPBIN/Section:. Debug $ T/rawData** `objectname` **. obj**.

Można również kompilować z [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), aby nie trzeba było używać PDB, lub usunąć opcję [/Debug](../../build/reference/debug-generate-debug-info.md) konsolidatora, jeśli nie ma plików. pdb dla obiektów, które tworzysz.
