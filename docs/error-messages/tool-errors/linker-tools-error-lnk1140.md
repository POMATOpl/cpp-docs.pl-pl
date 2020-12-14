---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1140'
title: Błąd narzędzi konsolidatora LNK1140
ms.date: 11/04/2016
f1_keywords:
- LNK1140
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
ms.openlocfilehash: cde57e3594035aecc1cc3608d1329c5bc0752624
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281200"
---
# <a name="linker-tools-error-lnk1140"></a>Błąd narzędzi konsolidatora LNK1140

za dużo modułów dla bazy danych programu; Połącz z/PDB: brak

Projekt zawiera więcej niż 4096 modułów.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aby rozwiązać ten problem, można użyć następujących rozwiązań

1. Połącz ponownie przy użyciu [/PDB: none](../../build/reference/pdb-use-program-database.md).

1. Kompiluj niektóre moduły bez informacji o debugowaniu.

1. Zmniejsz liczbę modułów.
