---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1305'
title: Błąd krytyczny C1305
ms.date: 11/04/2016
f1_keywords:
- C1305
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
ms.openlocfilehash: 100046d5ad7c6fa943358063d3d3cb21ffa00e5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267901"
---
# <a name="fatal-error-c1305"></a>Błąd krytyczny C1305

Baza danych profilów "pgd_file" jest dla innej architektury

Plik. PGD wygenerowany z/LTCG: PGINSTRUMENT operacji dla innej platformy został przekazano do [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Optymalizacje oparte na profilach](../../build/profile-guided-optimizations.md) są dostępne dla platform x86 i x64. Jednak plik. PGD wygenerowany przy użyciu operacji/LTCG: PGINSTRUMENT dla jednej platformy nie jest prawidłowy jako dane wejściowe do/LTCG: PGOPTIMIZE dla innej platformy.

Aby rozwiązać ten problem, należy przekazać plik. pgd, który został utworzony za pomocą/LTCG: PGINSTRUMENT do/LTCG: PGOPTIMIZE na tej samej platformie.
