---
description: 'Dowiedz się więcej o: błąd kompilatora C3838'
title: Błąd kompilatora C3838
ms.date: 11/04/2016
f1_keywords:
- C3838
helpviewer_keywords:
- C3838
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
ms.openlocfilehash: 9ea5f250b7a881ab9be6724f84dac418eefc705e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249150"
---
# <a name="compiler-error-c3838"></a>Błąd kompilatora C3838

nie można jawnie dziedziczyć po elemencie "Type"

Określony `type` element nie może działać jako klasa bazowa w żadnej klasie.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3838:

```cpp
// C3838a.cpp
// compile with: /clr /c
public ref class B : public System::Enum {};   // C3838
```
