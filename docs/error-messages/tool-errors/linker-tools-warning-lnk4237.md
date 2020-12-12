---
description: 'Dowiedz się więcej o: LNK4237 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4237 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4237
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
ms.openlocfilehash: 9f8af2d6f0fa2d1153af749e327e95b863ed6914
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259997"
---
# <a name="linker-tools-warning-lnk4237"></a>Ostrzeżenie LNK4237 narzędzi konsolidatora

/SUBSYSTEM: NATYWNy określony podczas importowania z "dll"; Użyj/SUBSYSTEM: CONSOLE lub/SUBSYSTEM: WINDOWS.

[/SUBSYSTEM:](../../build/reference/subsystem-specify-subsystem.md) podczas kompilowania aplikacji systemu Windows (Win32) został określony kod natywny, który bezpośrednio używa co najmniej jednego z następujących elementów:

- kernel32.dll

- gdi32.dll

- user32.dll

- Jedna z \* bibliotek dll msvcrt.

Usuń to ostrzeżenie, nie określając **/SUBSYSTEM: Native**.
