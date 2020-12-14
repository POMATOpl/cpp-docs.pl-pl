---
description: 'Dowiedz się więcej o: błąd kompilatora C3251'
title: Błąd kompilatora C3251
ms.date: 11/04/2016
f1_keywords:
- C3251
helpviewer_keywords:
- C3251
ms.assetid: 541c163e-5ee9-457c-a1e5-da860788b10d
ms.openlocfilehash: c8f5bf31920b5f6095a89f65884fee24491eb9e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307096"
---
# <a name="compiler-error-c3251"></a>Błąd kompilatora C3251

nie można wywołać metody klasy bazowej dla wystąpienia typu wartościowego

Następujący błąd występuje, ponieważ `GetClass` jest elementem członkowskim `Microsoft.Runtime.Object` , a nie `Microsoft.Runtime.Integer4` .
