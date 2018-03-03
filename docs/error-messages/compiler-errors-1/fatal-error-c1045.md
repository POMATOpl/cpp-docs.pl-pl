---
title: "Błąd krytyczny C1045 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1045
dev_langs:
- C++
helpviewer_keywords:
- C1045
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce780ee4f9299f9e5fd72e101115fc055d0f5920
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1045"></a>Błąd krytyczny C1045
ograniczenie kompilatora: powiązanie konsolidacji zagnieżdżono zbyt głęboko  
  
 Zagnieżdżone externals przekracza limit kompilatora. Zagnieżdżone externals są dozwolone z typem połączenie zewnętrzne, takie jak `extern` "C++". Zmniejsz liczbę zagnieżdżonych externals, aby rozwiązać problem.