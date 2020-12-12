---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1073'
title: Błąd krytyczny NMAKE U1073
ms.date: 11/04/2016
f1_keywords:
- U1073
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
ms.openlocfilehash: bd622f37720cf5e992a1d82ea97ca1ff50344c0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345449"
---
# <a name="nmake-fatal-error-u1073"></a>Błąd krytyczny NMAKE U1073

nie wiadomo, jak utworzyć element "TargetName"

Określony element docelowy nie istnieje i nie ma polecenia do wykonania lub wnioskowania o zastosowanie reguły.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aby rozwiązać ten problem, można użyć następujących rozwiązań

1. Sprawdź pisownię nazwy docelowej.

1. Jeśli *TargetName* jest pseudotarget, określ ją jako element docelowy w innym bloku opisu.

1. Jeśli *TargetName* jest wywołaniem makra, upewnij się, że nie jest rozwinięty do pustego ciągu.
