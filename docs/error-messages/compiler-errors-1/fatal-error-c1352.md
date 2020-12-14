---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1352'
title: Błąd krytyczny C1352
ms.date: 11/04/2016
f1_keywords:
- C1352
helpviewer_keywords:
- C1352
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
ms.openlocfilehash: 6838d3e095616d576ff1a709d4d82f879eb9e464
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276559"
---
# <a name="fatal-error-c1352"></a>Błąd krytyczny C1352

Nieprawidłowe lub uszkodzone MSIL w funkcji "Function" z modułu "File"

Do kompilatora został przekazano element. module, ale kompilator wykrył uszkodzenie w pliku.  Poproszenie osoby, która wyprodukowała moduł.

Kompilator nie sprawdza plików modułu dla wszystkich typów uszkodzeń.  Należy jednak sprawdzić, czy wszystkie ścieżki kontroli w funkcji zawierają instrukcję return.

Aby uzyskać więcej informacji, zobacz [. moduły plików jako dane wejściowe konsolidatora](../../build/reference/netmodule-files-as-linker-input.md).
