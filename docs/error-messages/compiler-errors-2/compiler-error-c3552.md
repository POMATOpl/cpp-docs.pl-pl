---
title: Błąd kompilatora C3552
ms.date: 11/04/2016
f1_keywords:
- C3552
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
ms.openlocfilehash: 567c92ddabbe2517700e4c67ef2c1ba899baada8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200671"
---
# <a name="compiler-error-c3552"></a>Błąd kompilatora C3552

"typename": określony typ zwracany przez późny nie może zawierać elementu "Auto"

Jeśli używasz słowa kluczowego `auto` jako symbolu zastępczego dla zwracanego typu funkcji, musisz podać typ zwracany z opóźnieniem. Nie można jednak użyć innego słowa kluczowego `auto`, aby określić typ zwracany określony jako opóźniony. Na przykład poniższy fragment kodu powoduje zwrócenie błędu C3552.

`auto myFunction->auto; // C3552`
