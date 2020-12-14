---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1052'
title: Błąd krytyczny C1052
ms.date: 05/08/2017
f1_keywords:
- C1052
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
ms.openlocfilehash: 818210cc4c3658167de30b9e666c600695389330
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251742"
---
# <a name="fatal-error-c1052"></a>Błąd krytyczny C1052

> plik bazy danych programu "*filename*" został wygenerowany przez konsolidator przy użyciu parametru/Debug: Fastlink; Kompilator nie może zaktualizować takich plików PDB; Usuń go lub użyj/FD, aby określić inną nazwę pliku PDB

Kompilator nie może zaktualizować tych samych plików bazy danych (PDB) programu, które są generowane przez konsolidator, gdy określono opcję [/Debug: Fastlink](../../build/reference/debug-generate-debug-info.md) . Zwykle generowane przez kompilator pliki PDB i generowane przez konsolidator pliki PDB mają różne nazwy. Jeśli jednak są ustawione tak, aby używały tych samych nazw, ten błąd może wynikać z tego błędu.

Aby rozwiązać ten problem, można jawnie usunąć pliki PDB przed ponowną kompilacją lub można utworzyć różne nazwy dla plików PDB generowanych przez kompilator i wygenerowanych przez konsolidator.

Aby określić nazwę pliku PDB wygenerowaną przez kompilator w wierszu polecenia, użyj opcji kompilatora [/FD](../../build/reference/fd-program-database-file-name.md) . Aby określić nazwę pliku PDB wygenerowaną przez kompilator w IDE, Otwórz okno dialogowe **strony właściwości** dla projektu, a następnie na stronie **Właściwości konfiguracji**, **C/C++**, **pliki wyjściowe** ustaw właściwość **Nazwa pliku bazy danych programu** . Domyślnie ta właściwość jest `$(IntDir)vc$(PlatformToolsetVersion).pdb` .

Alternatywnie można ustawić nazwę pliku PDB wygenerowaną przez konsolidator. Aby określić nazwę pliku PDB wygenerowaną przez konsolidator w wierszu polecenia, użyj opcji konsolidatora [/PDB](../../build/reference/pdb-use-program-database.md) . Aby określić nazwę pliku PDB wygenerowaną przez konsolidatora w środowisku IDE, Otwórz okno dialogowe **strony właściwości** dla projektu, a następnie na stronie **Właściwości konfiguracji**, **konsolidator**, **debugowanie** , ustaw właściwość **Generuj plik bazy danych programu** . Domyślnie wartość tej właściwości to `$(OutDir)$(TargetName).pdb`.
