---
description: 'Dowiedz się więcej o: LNK4001 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4001 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4001
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
ms.openlocfilehash: ceae4b205a7d591eff6de6c745fc379d5422a0e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332042"
---
# <a name="linker-tools-warning-lnk4001"></a>Ostrzeżenie LNK4001 narzędzi konsolidatora

nie określono plików obiektów; używane biblioteki

Konsolidator przeszedł jeden lub więcej plików. lib, ale nie ma plików. obj.

Ponieważ konsolidator nie jest w stanie uzyskać dostępu do informacji w pliku lib, do którego może uzyskać dostęp w pliku. obj, to ostrzeżenie wskazuje, że trzeba będzie jawnie określić inne Opcje konsolidatora. Na przykład może być konieczne określenie opcji [/Machine](../../build/reference/machine-specify-target-platform.md), [/out](../../build/reference/out-output-file-name.md)lub [/entry](../../build/reference/entry-entry-point-symbol.md) .
