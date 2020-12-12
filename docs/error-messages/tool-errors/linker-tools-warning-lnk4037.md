---
description: 'Dowiedz się więcej o: LNK4037 ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie narzędzi konsolidatora LNK4037
ms.date: 10/04/2017
f1_keywords:
- LNK4037
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
ms.openlocfilehash: 78fd5ed9f8e2f82221b64053607846f1b8abc00a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331952"
---
# <a name="linker-tools-warning-lnk4037"></a>Ostrzeżenie narzędzi konsolidatora LNK4037

>"*symbol*" nie istnieje; Ignoruj

Nie można zamówić *symbolicznej* nazwy przy użyciu opcji [/Order](../../build/reference/order-put-functions-in-order.md) , ponieważ nie można jej znaleźć w programie. Sprawdź specyfikację *symbolu* w pliku odpowiedzi porządkowania. Aby uzyskać więcej informacji, zobacz [/Order (Put Functions in order)](../../build/reference/order-put-functions-in-order.md) — opcja konsolidatora.

> [!NOTE]
> LINK nie może zamówić funkcji statycznych, ponieważ nazwy funkcji statycznych nie są nazwami symboli publicznych. Gdy **/Order** jest określony, to ostrzeżenie konsolidatora jest generowane dla każdego symbolu w pliku odpowiedzi zamówienia, który jest statyczny lub nie został znaleziony.
