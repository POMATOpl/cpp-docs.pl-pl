---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1210'
title: Błąd krytyczny C1210
ms.date: 11/04/2016
f1_keywords:
- C1210
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
ms.openlocfilehash: 6437d5894b0f3b4156dedc53f1a121ba85e7516f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267953"
---
# <a name="fatal-error-c1210"></a>Błąd krytyczny C1210

> /CLR: Pure i/CLR: Safe nie są obsługiwane przez zainstalowaną wersję środowiska uruchomieniowego w trakcie wykonania

**/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

C1210 występuje, gdy masz kompilator dla bieżącej wersji, ale środowisko uruchomieniowe języka wspólnego z poprzedniej wersji.

Niektóre funkcje kompilatora mogą nie działać w poprzedniej wersji czasu wykonywania.

Aby rozwiązać ten problem, C1210 Zainstaluj wersję środowiska uruchomieniowego języka wspólnego, która jest przeznaczona do użycia z kompilatorem.
