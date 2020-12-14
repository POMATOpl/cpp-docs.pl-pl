---
description: 'Dowiedz się więcej o: błąd kompilatora C3728'
title: Błąd kompilatora C3728
ms.date: 11/04/2016
f1_keywords:
- C3728
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
ms.openlocfilehash: 0cfcbd38928a153e3f5a58c1ec66b7e1c5bfd08d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245099"
---
# <a name="compiler-error-c3728"></a>Błąd kompilatora C3728

"zdarzenie": zdarzenie nie ma metody podniesienia

Metadane utworzone przy użyciu języka, takiego jak C#, które nie zezwalają na wywoływanie zdarzenia spoza klasy, w której zostały zdefiniowane, zostały dołączone do dyrektywy [#using](../../preprocessor/hash-using-directive-cpp.md) , a program Visual C++ przy użyciu środowiska CLR próbował wywołać zdarzenie.

Aby zgłosić zdarzenie w programie opracowanym w języku, takim jak C#, Klasa zawierająca zdarzenie musi także definiować metodę publiczną, która wywołuje zdarzenie.
