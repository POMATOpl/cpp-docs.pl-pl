---
description: 'Dowiedz się więcej o: Przestarzałe konwencje wywoływania'
title: Przestarzałe konwencje wywoływania
ms.date: 11/04/2016
f1_keywords:
- __fortran
- __pascal
- __syscall
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
ms.openlocfilehash: 0dfbb34215ba79b54d01ce12fe4d543dbe1d6859
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146045"
---
# <a name="obsolete-calling-conventions"></a>Przestarzałe konwencje wywoływania

**Specyficzne dla firmy Microsoft**

Konwencje wywoływania **__pascal**, **__fortran** i **__syscall** nie są już obsługiwane. Można emulować ich funkcje przy użyciu jednej z obsługiwanych konwencji wywoływania i odpowiednich opcji konsolidatora.

\<windows.h> obsługuje teraz makro WINAPI, które tłumaczy do odpowiedniej konwencji wywoływania dla elementu docelowego. Użyj WINAPI, w której wcześniej użyto języka PASCALa lub **__far \_ _pascal**.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Przekazywanie argumentów i konwencje nazewnictwa](../cpp/argument-passing-and-naming-conventions.md)
