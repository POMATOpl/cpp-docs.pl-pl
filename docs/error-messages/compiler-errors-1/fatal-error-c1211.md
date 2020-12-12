---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1211'
title: Błąd krytyczny C1211
ms.date: 11/04/2016
f1_keywords:
- C1211
helpviewer_keywords:
- C1211
ms.assetid: df0ca70d-ec6e-4400-926a-b877e2599978
ms.openlocfilehash: b2b3c0d3a918704d700d61a74964483f20eb8a51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267940"
---
# <a name="fatal-error-c1211"></a>Błąd krytyczny C1211

Atrybut niestandardowy TypeForwardedTo nie jest obsługiwany przez zainstalowaną wersję środowiska uruchomieniowego w trakcie wykonania

C1211 występuje, gdy masz kompilator dla bieżącej wersji, ale środowisko uruchomieniowe języka wspólnego z poprzedniej wersji.

Niektóre funkcje kompilatora mogą nie działać w poprzedniej wersji czasu wykonywania.

Aby rozwiązać C1211, zainstaluj środowisko uruchomieniowe języka wspólnego, które zostało dostarczone z używanym kompilatorem.

Aby uzyskać więcej informacji, zobacz [przekazywanie dalej typu (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).
