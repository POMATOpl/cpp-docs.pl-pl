---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4678'
title: Ostrzeżenie kompilatora (poziom 1) C4678
ms.date: 11/04/2016
f1_keywords:
- C4678
helpviewer_keywords:
- C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
ms.openlocfilehash: a590bd03ba73fc4f8d5421727e5e35ac1384ffaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285386"
---
# <a name="compiler-warning-level-1-c4678"></a>Ostrzeżenie kompilatora (poziom 1) C4678

Klasa bazowa "base_type" jest mniej dostępna niż "derived_type"

Typ publiczny pochodzi z typu prywatnego. Jeśli typ publiczny jest skonkretyzowany w przywoływanym zestawie, elementy członkowskie typu prywatnego nie będą dostępne.

C4678 jest osiągalna tylko przy użyciu przestarzałej opcji kompilatora **/CLR: oldSyntax**. Wystąpił błąd podczas używania **/CLR**, aby mieć klasę bazową, która jest mniej dostępna dla jej klasy pochodnej.
