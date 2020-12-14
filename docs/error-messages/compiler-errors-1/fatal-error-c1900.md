---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1900'
title: Błąd krytyczny C1900
ms.date: 11/04/2016
f1_keywords:
- C1900
helpviewer_keywords:
- C1900
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
ms.openlocfilehash: e7bcd44846f34b3d3910d4c1aac292ee6414b439
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276117"
---
# <a name="fatal-error-c1900"></a>Błąd krytyczny C1900

> Niezgodność Il między "*Tool1*" w wersji "*Liczba1*" i "*Tool2*" w wersji "*liczba2*"

Narzędzia działające w różnych przebiegach kompilatora nie są zgodne. *Liczba1* i *liczba2* zapoznaj się z datami plików. Na przykład w przypadku przebiegu 1 są uruchamiane frontony kompilatora (c1.dll) i w przebiegu 2, działające na zapleczu kompilatora (c2.dll). Daty w plikach muszą być zgodne.

Aby rozwiązać ten problem, upewnij się, że wszystkie aktualizacje zostały zastosowane do programu Visual Studio. Jeśli problem nie zniknie, użyj **apletu programy i funkcje** w panelu sterowania systemu Windows, aby naprawić lub ponownie zainstalować program Visual Studio.
