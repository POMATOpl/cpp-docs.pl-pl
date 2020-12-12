---
description: 'Dowiedz się więcej o: błąd kompilatora C3234'
title: Błąd kompilatora C3234
ms.date: 11/04/2016
f1_keywords:
- C3234
helpviewer_keywords:
- C3234
ms.assetid: ebefc15a-e40d-424b-a3dd-d7e185d0ed7b
ms.openlocfilehash: 8e43b4ae7151d3be32ffc18ccec9995de67c21cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311971"
---
# <a name="compiler-error-c3234"></a>Błąd kompilatora C3234

Klasa generyczna nie może pochodzić z parametru typu ogólnego

Klasa generyczna nie może dziedziczyć z parametru typu ogólnego.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3234.

```cpp
// C3234.cpp
// compile with: /clr /c
generic <class T>
public ref class C : T {};   // C3234
// try the following line instead
// public ref class C {};
```
