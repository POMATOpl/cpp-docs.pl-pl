---
description: 'Dowiedz się więcej na temat: memccpy'
title: memccpy
ms.date: 12/16/2019
api_name:
- memccpy
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
- memccpy
helpviewer_keywords:
- memccpy function
ms.assetid: e9951812-2b69-43e9-bbee-a0001bce4d80
ms.openlocfilehash: 5a8fdbe09ceb8ba4c53037999eafd2e282d59ed6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117305"
---
# <a name="memccpy"></a>memccpy

Nazwa funkcji platformy POSIX wdrożonej przez firmę Microsoft `memccpy` jest przestarzałym aliasem dla funkcji [_memccpy](memccpy.md) . Domyślnie generuje [Ostrzeżenie kompilatora (poziom 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Nazwa jest przestarzała, ponieważ nie jest zgodna z regułami standard C dla nazw specyficznych dla implementacji. Jednak funkcja jest nadal obsługiwana.

Zalecamy używanie [_memccpy](memccpy.md) . Możesz również nadal używać tej nazwy funkcji i wyłączyć ostrzeżenie. Aby uzyskać więcej informacji, zobacz Wyłączanie [nazw funkcji](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names) [Warning](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) i POSIX.
