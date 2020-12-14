---
description: 'Dowiedz się więcej na temat: BSCMAKE Warning BK4504'
title: Ostrzeżenie BSCMAKE BK4504
ms.date: 11/04/2016
f1_keywords:
- BK4504
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
ms.openlocfilehash: 8b07c15b03a040ea19ec368c6f869d02f3e36f79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237832"
---
# <a name="bscmake-warning-bk4504"></a>Ostrzeżenie BSCMAKE BK4504

plik zawiera zbyt wiele odwołań; ignorowanie dalszych odwołań z tego źródła

Plik. cpp zawiera więcej niż 64 000 odwołań do symboli. Gdy BSCMAKE napotkała odwołania do 64 000 w pliku, ignoruje wszystkie dalsze odwołania.

Aby rozwiązać ten problem, należy podzielić plik na co najmniej dwa pliki, z których każdy ma mniej niż 64 000 odwołań do symboli lub użyć `#pragma component(browser)` dyrektywy preprocesora w celu ograniczenia symboli, które są generowane dla określonych odwołań. Aby uzyskać więcej informacji, zobacz [składnik](../../preprocessor/component.md).
