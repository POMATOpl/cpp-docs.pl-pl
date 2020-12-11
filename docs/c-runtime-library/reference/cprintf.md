---
description: 'Dowiedz się więcej na temat: cprintf'
title: cprintf
ms.date: 12/16/2019
api_name:
- cprintf
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- cprintf
helpviewer_keywords:
- cprintf function
ms.assetid: 573e6634-d7e5-4856-8c01-627dcfbd5fc8
ms.openlocfilehash: c42a02afaaa820e58f32b251ad760cf3bee825ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155907"
---
# <a name="cprintf"></a>cprintf

Nazwa funkcji specyficznej dla firmy Microsoft `cprintf` jest przestarzałym aliasem funkcji [_cprintf](cprintf-cprintf-l-cwprintf-cwprintf-l.md) . Domyślnie generuje [Ostrzeżenie kompilatora (poziom 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Nazwa jest przestarzała, ponieważ nie jest zgodna z regułami standard C dla nazw specyficznych dla implementacji. Jednak funkcja jest nadal obsługiwana.

Zaleca się zamiast tego użycie funkcji [_cprintf_s](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md) [_cprintf](cprintf-cprintf-l-cwprintf-cwprintf-l.md) lub ulepszonej zabezpieczeniami. Możesz również nadal używać tej nazwy funkcji i wyłączyć ostrzeżenie. Aby uzyskać więcej informacji, zobacz Wyłączanie [nazw funkcji](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names) [Warning](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) i POSIX.

> [!IMPORTANT]
> Tego interfejsu API nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows. Aby uzyskać więcej informacji, zobacz [funkcje CRT nieobsługiwane w aplikacjach platforma uniwersalna systemu Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).
