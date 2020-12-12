---
description: 'Dowiedz się więcej na temat: NMAKE Warning U4010'
title: Ostrzeżenie NMAKE U4010
ms.date: 11/04/2016
f1_keywords:
- U4010
helpviewer_keywords:
- U4010
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
ms.openlocfilehash: d0c72044576ebf3441fdec7980c933edec671097
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334800"
---
# <a name="nmake-warning-u4010"></a>Ostrzeżenie NMAKE U4010

"target": kompilacja nie powiodła się; Określono/k, kontynuowanie...

Polecenie w bloku poleceń dla danego elementu docelowego zwróciło niezerowy kod zakończenia. Opcja/K poinformowała NMAKE, aby kontynuować przetwarzanie niepowiązanych części kompilacji i wydać kod zakończenia 1 po zakończeniu sesji NMAKE.

Jeśli dany obiekt docelowy jest, zależny od innego elementu docelowego, NMAKE wystawia ostrzeżenie [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) po tym ostrzeżeniu.
