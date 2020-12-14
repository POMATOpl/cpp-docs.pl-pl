---
description: 'Dowiedz się więcej na temat: NMAKE Warning U4004'
title: Ostrzeżenie NMAKE U4004
ms.date: 11/04/2016
f1_keywords:
- U4004
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
ms.openlocfilehash: 44326bfb6a69b583967163054b4510bf5c50d6bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345293"
---
# <a name="nmake-warning-u4004"></a>Ostrzeżenie NMAKE U4004

zbyt wiele reguł dla elementu docelowego "TargetName"

Określono więcej niż jeden blok opisu dla danego obiektu docelowego przy użyciu pojedynczych dwukropków (**:**) jako separatorów. NMAKE wykonał polecenia w pierwszym bloku opisu i zignorował późniejsze bloki.

Aby określić ten sam element docelowy w wielu zależnościach, użyj podwójnego dwukropka ( `::` ) jako separatora w każdej linii zależności.
