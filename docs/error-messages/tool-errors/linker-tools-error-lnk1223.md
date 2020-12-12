---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1223'
title: Błąd narzędzi konsolidatora LNK1223
ms.date: 11/04/2016
f1_keywords:
- LNK1223
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
ms.openlocfilehash: eb1937f253d324781834d0b6f465c79f7009787f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194062"
---
# <a name="linker-tools-error-lnk1223"></a>Błąd narzędzi konsolidatora LNK1223

nieprawidłowy lub uszkodzony plik: plik zawiera nieprawidłowe udziały pData

W przypadku platform RISC wykorzystujących pData ten błąd wystąpi, jeśli kompilator emituje sekcję. pdata z nieposortowanymi wpisami.

Aby rozwiązać ten problem, należy wykonać kompilację bez włączonej [/GL (Optymalizacja całego programu)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) . Puste treści funkcji mogą również spowodować wystąpienie tego błędu w niektórych przypadkach.
