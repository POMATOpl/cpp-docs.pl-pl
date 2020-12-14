---
description: 'Dowiedz się więcej o: błąd kompilatora C3610'
title: Błąd kompilatora C3610
ms.date: 11/04/2016
f1_keywords:
- C3610
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
ms.openlocfilehash: 0fca8f57fcdf2e935620118092708ba1c94f5ec0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223142"
---
# <a name="compiler-error-c3610"></a>Błąd kompilatora C3610

"ValueType": typ wartości musi być "opakowany" przed wywołaniem metody "Method"

Domyślnie typ wartości nie znajduje się na zarządzanym stosie. Przed wywołaniem metod z klas środowiska uruchomieniowego platformy .NET, takich jak `Object` , należy przenieść typ wartości do sterty zarządzanej.

C3610 jest osiągalna tylko przy użyciu przestarzałej opcji kompilatora **/CLR: oldSyntax**.
