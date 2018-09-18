---
title: Błąd krytyczny C1091 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1091
dev_langs:
- C++
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e93c2e6c26f8704e700465fb706867129847a460
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104256"
---
# <a name="fatal-error-c1091"></a>Błąd krytyczny C1091

ograniczenie kompilatora: ciąg przekracza "length" bajtów długości

Stała typu string przekracza bieżący limit długości ciągów.

Warto podzielić ciąg statyczne zmienne (co najmniej dwa) i używać [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) do dołączenia do wyniku jako część deklaracji lub w czasie wykonywania.