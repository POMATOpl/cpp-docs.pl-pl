---
title: "Błąd BSCMAKE BK1517 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1517
dev_langs: C++
helpviewer_keywords: BK1517
ms.assetid: 24391f42-0a3e-40a9-9991-c8b9a6a7b1c7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5978ceab4a5a5e768ddda635398466bb941c42cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1517"></a>Błąd BSCMAKE BK1517
plik źródłowy sbrfile skompilowana przy użyciu opcji /Yc i /Yu  
  
 Plik .sbr odwołuje się do siebie. Go została prawdopodobnie ponownie skompilowana z /Yu po kompilacji z /Yc. Przywrócić /Yc — opcja kompilatora dla pliku źródłowego, a następnie wybierz **odbudować** wygenerować nowe pliki .sbr. Nie zostanie ponownie skompilowana z /Yu pliku źródłowego.