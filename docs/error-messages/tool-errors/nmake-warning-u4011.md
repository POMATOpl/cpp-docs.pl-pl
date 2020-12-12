---
description: 'Dowiedz się więcej na temat: NMAKE Warning U4011'
title: Ostrzeżenie NMAKE U4011
ms.date: 11/04/2016
f1_keywords:
- U4011
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
ms.openlocfilehash: b421dff75ea0ecbdbc454053db3912e3f3e47ded
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164240"
---
# <a name="nmake-warning-u4011"></a>Ostrzeżenie NMAKE U4011

"target": nie wszystkie elementy zależne są dostępne; obiekt docelowy nie został skompilowany

Zależna od danego elementu docelowego nie istniała lub była nieaktualna, a polecenie aktualizacji elementu zależnego zwróciło niezerowy kod zakończenia. Opcja/K poinformowała NMAKE, aby kontynuować przetwarzanie niepowiązanych części kompilacji i wydać kod zakończenia 1 po zakończeniu sesji NMAKE.

To ostrzeżenie jest poprzedzone ostrzeżeniem [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) dla każdego elementu zależnego, który nie został utworzony ani zaktualizowany.
