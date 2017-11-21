---
title: "Błąd krytyczny C1045 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1045
dev_langs: C++
helpviewer_keywords: C1045
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 523c717f2e3e3e7485cfbd1f4c2e7bf270b4e6a3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1045"></a>Błąd krytyczny C1045
ograniczenie kompilatora: powiązanie konsolidacji zagnieżdżono zbyt głęboko  
  
 Zagnieżdżone externals przekracza limit kompilatora. Zagnieżdżone externals są dozwolone z typem połączenie zewnętrzne, takie jak `extern` "C++". Zmniejsz liczbę zagnieżdżonych externals, aby rozwiązać problem.