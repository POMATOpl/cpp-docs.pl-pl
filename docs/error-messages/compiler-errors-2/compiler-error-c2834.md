---
description: 'Dowiedz się więcej o: błąd kompilatora C2834'
title: Błąd kompilatora C2834
ms.date: 11/04/2016
f1_keywords:
- C2834
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
ms.openlocfilehash: 6f74853f264af653988ed77ddb9a9c7935f3c542
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194439"
---
# <a name="compiler-error-c2834"></a>Błąd kompilatora C2834

operator "operator" musi być globalnie kwalifikowany

`new`Operatory i `delete` są powiązane z klasą, gdzie się znajdują. Nie można użyć rozpoznawania zakresu w celu wybrania wersji `new` lub `delete` z innej klasy. Aby zaimplementować wiele form `new` `delete` operatora OR, Utwórz wersję operatora z dodatkowymi parametrami formalnymi.
