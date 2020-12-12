---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4952'
title: Ostrzeżenie kompilatora (poziom 1) C4952
ms.date: 08/27/2018
f1_keywords:
- C4952
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
ms.openlocfilehash: afbc12f6e4e8219c541acd846a3752a331abe827
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327950"
---
# <a name="compiler-warning-level-1-c4952"></a>Ostrzeżenie kompilatora (poziom 1) C4952

> "*Function*": nie znaleziono danych profilowych w bazie danych programu "*pgd_file*"

W przypadku korzystania z [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)Kompilator wykrył Moduł wejściowy, który został ponownie skompilowany po `/LTCG:PGINSTRUMENT` i ma nową funkcję (*funkcję*).

To ostrzeżenie jest informacje. Aby usunąć to ostrzeżenie, uruchom `/LTCG:PGINSTRUMENT` polecenie, wykonaj ponownie wszystkie przebiegi testowe i uruchom polecenie `/LTCG:PGOPTIMIZE` .

To ostrzeżenie zostanie zastąpione błędem, jeśli `/LTCG:PGOPTIMIZE` był używany.
