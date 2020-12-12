---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1026'
title: Błąd krytyczny C1026
ms.date: 11/04/2016
f1_keywords:
- C1026
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
ms.openlocfilehash: 08816f21879cf6dfbeb0389700d9a8ffdc7a40d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345514"
---
# <a name="fatal-error-c1026"></a>Błąd krytyczny C1026

przepełnienie stosu parsera, zbyt skomplikowany program

Miejsce wymagane do przeanalizowania programu spowodowało przepełnienie stosu kompilatora.

Zmniejsz złożoność wyrażeń przez:

- Zmniejszenie zagnieżdżenia w **`for`** **`switch`** instrukcjach i. Umieść bardziej głęboko zagnieżdżone instrukcje w osobnych funkcjach.

- Przerywanie długich wyrażeń, które obejmują operatory przecinkowe lub wywołania funkcji.
