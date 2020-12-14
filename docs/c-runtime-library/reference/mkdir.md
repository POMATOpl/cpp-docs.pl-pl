---
description: 'Dowiedz się więcej na temat: mkdir'
title: mkdir
ms.date: 12/16/2019
api_name:
- mkdir
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
- mkdir
helpviewer_keywords:
- mkdir function
ms.assetid: 0a212890-181e-45d0-988d-e0f301fcdeb8
ms.openlocfilehash: a32fe98b6b6c60828ca1f366627c818b9dd8c29f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186665"
---
# <a name="mkdir"></a>mkdir

Nazwa funkcji platformy POSIX wdrożonej przez firmę Microsoft `mkdir` jest przestarzałym aliasem dla funkcji [_mkdir](mkdir-wmkdir.md) . Domyślnie generuje [Ostrzeżenie kompilatora (poziom 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Nazwa jest przestarzała, ponieważ nie jest zgodna z regułami standard C dla nazw specyficznych dla implementacji. Jednak funkcja jest nadal obsługiwana.

Zalecamy używanie [_mkdir](mkdir-wmkdir.md) . Możesz również nadal używać tej nazwy funkcji i wyłączyć ostrzeżenie. Aby uzyskać więcej informacji, zobacz Wyłączanie [nazw funkcji](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names) [Warning](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) i POSIX.
