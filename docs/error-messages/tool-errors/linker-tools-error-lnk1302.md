---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1302'
title: Błąd narzędzi konsolidatora LNK1302
ms.date: 11/04/2016
f1_keywords:
- LNK1302
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
ms.openlocfilehash: 33e9a406cde7910c7340fdfe256711c47eee45cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193698"
---
# <a name="linker-tools-error-lnk1302"></a>Błąd narzędzi konsolidatora LNK1302

Obsługiwane są tylko łączenie bezpiecznych modułów. nie można połączyć pliku. module

Moduł. (skompilowany za pomocą **/LN**) został przekazano do konsolidatora w próbie wywołania elementu MSIL.  Moduł C++ jest prawidłowy w przypadku łączenia MSIL, jeśli jest kompilowany z **/CLR: Safe**.

Aby naprawić ten błąd, skompiluj z **/CLR: Safe** , aby włączyć łączenie MSIL, lub Przekaż plik **/CLR** lub **/CLR: Pure** . obj zamiast modułu.

Aby uzyskać więcej informacji, zobacz

- [/LN (Utwórz moduł MSIL)](../../build/reference/ln-create-msil-module.md)

- [Pliki. module — Wejście konsolidatora](../../build/reference/netmodule-files-as-linker-input.md)
