---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK2023'
title: Błąd narzędzi konsolidatora LNK2023
ms.date: 11/04/2016
f1_keywords:
- LNK2023
helpviewer_keywords:
- LNK2023
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
ms.openlocfilehash: fbcddcb00d77fd1b51effb27bc032019fc803d3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275818"
---
# <a name="linker-tools-error-lnk2023"></a>Błąd narzędzi konsolidatora LNK2023

Nieprawidłowa Biblioteka DLL lub punkt wejścia \<dll or entry point>

Konsolidator ładuje niepoprawną wersję msobj90.dll. Upewnij się, że link.exe i msobj90.dll w ścieżce mają tę samą wersję.

Zależność msobj90.dll może nie być obecna. Lista zależności dla msobj90.dll jest:

- Msvcr90.dll

- Kernel32.dll

Sprawdź, czy na maszynie istnieje inna kopia msobj90.dll, która może być nieaktualna.
