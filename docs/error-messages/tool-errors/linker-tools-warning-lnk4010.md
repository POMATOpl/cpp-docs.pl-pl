---
title: Ostrzeżenie LNK4010 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4010
helpviewer_keywords:
- LNK4010
ms.assetid: 2824cf99-4174-4b60-a6e2-c01e9f1ee52d
ms.openlocfilehash: 5b2d5bd9b9d2fe0af488dad000638e7ae4f7624d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194307"
---
# <a name="linker-tools-warning-lnk4010"></a>Ostrzeżenie LNK4010 narzędzi konsolidatora

nieprawidłowy numer wersji podsystemu; przyjęto domyślną wersję podsystemu

Możesz określić wersję podsystemu obrazu ([/Subsystem](../../build/reference/subsystem-specify-subsystem.md)). Każdy podsystem ma minimalne wymagania dotyczące wersji. Jeśli określona wersja jest niższa niż wartość minimalna, to ostrzeżenie zostanie wykonane, a konsolidator użyje tylko domyślnego podsystemu.
