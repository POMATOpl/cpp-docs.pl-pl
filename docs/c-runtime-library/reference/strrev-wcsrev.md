---
description: 'Dowiedz się więcej o: strrev, wcsrev'
title: strrev, wcsrev
ms.date: 12/16/2019
api_name:
- strrev
- wcsrev
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
- strrev
- wcsrev
helpviewer_keywords:
- strrev function
- wcsrev function
ms.assetid: 89e05854-a9ce-4fb7-993d-a9831cd7edf2
ms.openlocfilehash: 2f9cb8e5a1a0bce09b0da030392d6b459f16c967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209428"
---
# <a name="strrev-wcsrev"></a>strrev, wcsrev

Nazwy funkcji specyficznych dla firmy Microsoft `strrev` i `wcsrev` są przestarzałe aliasy dla funkcji [_strrev i _wcsrev](strrev-wcsrev-mbsrev-mbsrev-l.md) . Domyślnie generują [ostrzeżenia kompilatora (poziom 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Nazwy są przestarzałe, ponieważ nie przestrzegają standardowych reguł języka C dla nazw specyficznych dla implementacji. Jednak funkcje są nadal obsługiwane.

Zalecamy używanie [_strrev i _wcsrev](strrev-wcsrev-mbsrev-mbsrev-l.md) . Możesz również nadal używać tych nazw funkcji i wyłączyć ostrzeżenie. Aby uzyskać więcej informacji, zobacz Wyłączanie [nazw funkcji](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names) [Warning](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) i POSIX.
