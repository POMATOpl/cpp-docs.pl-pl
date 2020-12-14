---
description: 'Dowiedz się więcej na temat: RC4005 ostrzeżenia kompilatora zasobów'
title: Ostrzeżenie RC4005 kompilatora zasobów
ms.date: 11/04/2016
f1_keywords:
- RC4005
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
ms.openlocfilehash: 138037e48356448550308abee8dc43cd06b9ac06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237130"
---
# <a name="resource-compiler-warning-rc4005"></a>Ostrzeżenie RC4005 kompilatora zasobów

"Identyfikator": Ponowna definicja makra

Identyfikator jest definiowany dwa razy. Kompilator użył drugiej definicji makra.

To ostrzeżenie może być spowodowane przez zdefiniowanie makra w wierszu polecenia i w kodzie za pomocą `#define` dyrektywy. Przyczyną może być również makra importowane z plików dołączanych.

Aby wyeliminować ostrzeżenie, Usuń jedną z definicji lub Użyj `#undef` dyrektywy przed drugą definicją.
