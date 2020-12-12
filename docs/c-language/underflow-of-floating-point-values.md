---
description: 'Dowiedz się więcej na temat: Niedopełnienie wartości Floating-Point'
title: Niedopełnienie wartości zmiennoprzecinkowych
ms.date: 11/04/2016
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
ms.openlocfilehash: 3d8ddd665aa33e1c47f9f187f759058501bc5484
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321300"
---
# <a name="underflow-of-floating-point-values"></a>Niedopełnienie wartości zmiennoprzecinkowych

**ANSI 4.5.1** Czy funkcja matematyki ustawia wyrażenie liczby całkowitej `errno` na wartość makra `ERANGE` w przypadku błędów zakresu niedopełnienia

Niedomiarowa zmiennoprzecinkowa nie ustawia wyrażenia `errno` na `ERANGE` . Gdy wartość zbliża się do zera i ostatecznie podpływa, wartość jest równa zero.

## <a name="see-also"></a>Zobacz też

[Funkcje biblioteki](../c-language/library-functions.md)
