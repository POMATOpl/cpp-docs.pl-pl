---
description: 'Dowiedz się więcej o: błąd kompilatora C2567'
title: Błąd kompilatora C2567
ms.date: 11/04/2016
f1_keywords:
- C2567
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
ms.openlocfilehash: 113dfebc1ac6bde6857ea55fd6249fff12c9faae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209116"
---
# <a name="compiler-error-c2567"></a>Błąd kompilatora C2567

nie można otworzyć metadanych w pliku "File", plik mógł zostać usunięty lub przeniesiony

Plik metadanych, do którego odwołuje się element source (with `#using` ), nie został odnaleziony w tym samym katalogu przez proces zaplecza kompilatora, ponieważ został on utworzony przez proces frontonu kompilatora. Aby uzyskać więcej informacji, zobacz [#using dyrektywie](../../preprocessor/hash-using-directive-cpp.md) .

C2567 może być spowodowana kompilacją z **/c** na jednym komputerze, a następnie próba generowania kodu w czasie konsolidacji na innym komputerze. Aby uzyskać więcej informacji, zobacz [/LTCG (generowanie kodu w czasie konsolidacji)](../../build/reference/ltcg-link-time-code-generation.md)).

Może również wskazywać, że komputer nie ma więcej pamięci.

Aby naprawić ten błąd, upewnij się, że plik metadanych znajduje się w tej samej lokalizacji katalogu dla wszystkich faz procesu kompilacji.
