---
title: 2.7.2.4 udostępnione | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c9c5d653-58fc-4620-ab0a-443ac4f8ba2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d1a545f1c505f9f578cad682399c8d69a882824
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400149"
---
# <a name="2724-shared"></a>2.7.2.4 — udostępnione

Ta klauzula udostępnia zmiennych, które pojawiają się w *liście zmiennych* przez wszystkie wątki w zespole. Wszystkie wątki w zespole dostęp do tego samego obszaru pamięci masowej **udostępnionego** zmiennych.

Składnia **udostępnionego** klauzula jest w następujący sposób:

```
shared(variable-list)
```