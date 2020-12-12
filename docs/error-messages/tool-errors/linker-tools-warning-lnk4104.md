---
description: 'Dowiedz się więcej o: LNK4104 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4104 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4104
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
ms.openlocfilehash: ab48885a4a8d2806154d3a8911bdc65453359e2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294434"
---
# <a name="linker-tools-warning-lnk4104"></a>Ostrzeżenie LNK4104 narzędzi konsolidatora

Eksport symbolu "symbol" powinien być prywatny

`symbol`Może to być jeden z następujących:

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllGetDocumentation`

- `DllInitialize`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllRegisterServerExW`

- `DllUnload`

- `DllUnregisterServer`

- `RasCustomDeleteEntryNotify`

- `RasCustomDial`

- `RasCustomDialDlg`

- `RasCustomEntryDlg`

To ostrzeżenie jest emitowane podczas tworzenia biblioteki importu dla biblioteki DLL i eksportowania jednej z powyższych funkcji bez określania jej jako prywatnego w pliku definicji modułu. Ogólnie rzecz biorąc, te funkcje są eksportowane do użycia tylko przez OLE. Umieszczenie ich w bibliotece import może prowadzić do nietypowego zachowania, gdy program połączony z biblioteką niepoprawnie wywołuje te wywołania. Aby uzyskać więcej informacji na temat prywatnego słowa kluczowego, zobacz [eksporty](../../build/reference/exports.md).
