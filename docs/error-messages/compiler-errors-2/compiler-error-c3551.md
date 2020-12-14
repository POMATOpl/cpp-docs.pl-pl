---
description: 'Dowiedz się więcej o: błąd kompilatora C3551'
title: Błąd kompilatora C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 813d483b696d0829f05108a35e5731f93f6004ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223272"
---
# <a name="compiler-error-c3551"></a>Błąd kompilatora C3551

"oczekiwany określony typ zwracany przez późny"

Jeśli używasz **`auto`** słowa kluczowego jako symbolu zastępczego dla zwracanego typu funkcji, musisz podać typ zwracany określony jako późny. W poniższym przykładzie typ zwracany funkcji z opóźnieniem `myFunction` jest wskaźnikiem do tablicy czterech elementów typu **`int`** .

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>Zobacz też

[Automatycznie](../../cpp/auto-cpp.md)
