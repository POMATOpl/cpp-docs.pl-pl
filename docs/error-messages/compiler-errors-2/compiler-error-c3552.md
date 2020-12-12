---
description: 'Dowiedz się więcej o: błąd kompilatora C3552'
title: Błąd kompilatora C3552
ms.date: 11/04/2016
f1_keywords:
- C3552
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
ms.openlocfilehash: aca1474f53c8ac1a8257b23d0042550b76b3c0e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223259"
---
# <a name="compiler-error-c3552"></a>Błąd kompilatora C3552

"typename": określony typ zwracany przez późny nie może zawierać elementu "Auto"

Jeśli używasz **`auto`** słowa kluczowego jako symbolu zastępczego dla zwracanego typu funkcji, musisz podać typ zwracany określony jako późny. Nie można jednak użyć innego **`auto`** słowa kluczowego, aby określić typ zwracany określony jako opóźniony. Na przykład poniższy fragment kodu powoduje zwrócenie błędu C3552.

`auto myFunction->auto; // C3552`
