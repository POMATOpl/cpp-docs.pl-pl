---
description: 'Dowiedz się więcej o: LNK4206 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4206 narzędzi konsolidatora
ms.date: 12/05/2017
f1_keywords:
- LNK4206
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
ms.openlocfilehash: 40d7a8f18a835721ff747293696d0499c0a94ef3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294148"
---
# <a name="linker-tools-warning-lnk4206"></a>Ostrzeżenie LNK4206 narzędzi konsolidatora

> nie znaleziono wstępnie skompilowanych informacji o typie; *plik "filename*" nie jest połączony ani nadpisany; Łączenie obiektu bez informacji debugowania

Plik obiektu *filename* , skompilowany za pomocą [/YC](../../build/reference/yc-create-precompiled-header-file.md), nie został określony w poleceniu linku lub został zastąpiony.

Typowym scenariuszem tego ostrzeżenia jest to, że obiekt. obj, który został skompilowany za pomocą/YC, znajduje się w bibliotece i gdzie nie ma odwołań do symboli do tego elementu. obj z kodu.  W takim przypadku konsolidator nie będzie używać (lub nawet wyświetlania) pliku. obj.  W takiej sytuacji należy ponownie skompilować kod i użyć [/yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) dla obiektów kompilowanych przy użyciu [/Yu](../../build/reference/yu-use-precompiled-header-file.md).
