---
description: 'Dowiedz się więcej na temat: Tworzenie'
title: creat
ms.date: 12/16/2019
api_name:
- creat
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
- creat
helpviewer_keywords:
- creat function
ms.assetid: 3aa6f0cc-5ae6-40d5-be94-0ab6f53c0c5b
ms.openlocfilehash: 62384a60fe36372a8ce65b51ffee8b918f312585
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340609"
---
# <a name="creat"></a>creat

Nazwa funkcji platformy POSIX wdrożonej przez firmę Microsoft `creat` jest przestarzałym aliasem dla funkcji [_creat](creat-wcreat.md) . Domyślnie generuje [Ostrzeżenie kompilatora (poziom 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Nazwa jest przestarzała, ponieważ nie jest zgodna z regułami standard C dla nazw specyficznych dla implementacji. Jednak funkcja jest nadal obsługiwana.

Zalecamy używanie [_creat](creat-wcreat.md) . Możesz również nadal używać tej nazwy funkcji i wyłączyć ostrzeżenie. Aby uzyskać więcej informacji, zobacz Wyłączanie [nazw funkcji](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names) [Warning](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) i POSIX.
