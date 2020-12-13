---
description: 'Dowiedz się więcej na temat: sopen'
title: sopen
ms.date: 12/16/2019
api_name:
- sopen
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
- sopen
helpviewer_keywords:
- sopen function
ms.assetid: 1ce0b707-0c9e-4942-8467-ce7f6cd68acc
ms.openlocfilehash: 14823b3c1c8bb0f266723fd138ba2c2bf6a4dbfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136906"
---
# <a name="sopen"></a>sopen

Nazwa funkcji specyficznej dla firmy Microsoft `sopen` jest przestarzałym aliasem funkcji [_sopen](sopen-wsopen.md) . Domyślnie generuje [Ostrzeżenie kompilatora (poziom 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Nazwa jest przestarzała, ponieważ nie jest zgodna z regułami standard C dla nazw specyficznych dla implementacji. Jednak funkcja jest nadal obsługiwana.

Zalecamy używanie [_sopen](sopen-wsopen.md) lub funkcji [_sopen_s](sopen-s-wsopen-s.md) ulepszonych z zabezpieczeniami. Możesz również nadal używać tej nazwy funkcji i wyłączyć ostrzeżenie. Aby uzyskać więcej informacji, zobacz Wyłączanie [nazw funkcji](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names) [Warning](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) i POSIX.
