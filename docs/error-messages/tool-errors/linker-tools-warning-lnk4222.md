---
description: 'Dowiedz się więcej o: LNK4222 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4222 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4222
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
ms.openlocfilehash: 215dd04339b783d558b05140bb7dd08c5936d5e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222610"
---
# <a name="linker-tools-warning-lnk4222"></a>Ostrzeżenie LNK4222 narzędzi konsolidatora

do wyeksportowanego symbolu "symbol" nie należy przypisywać liczby porządkowej

Następujące symbole nie powinny być eksportowane według numeru porządkowego:

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllUnregisterServer`

Te funkcje są zawsze zlokalizowane według nazwy, przy użyciu `GetProcAddress` . Konsolidator ostrzega o tym rodzaju eksportu, ponieważ może to skutkować większym obrazem. Taka sytuacja może wystąpić, jeśli zakres eksportów porządkowych jest duży z stosunkowo niewielkim eksportem. Przykład:

```
EXPORTS
   DllGetClassObject   @1
   MyOtherAPI      @100
```

Program będzie wymagał 100 gniazd w tabeli adresów eksportu z 98 z nich (2-99). Z drugiej strony

```
EXPORTS
   DllGetClassObject
   MyOtherAPI      @100
```

wymagane są dwa gniazda. Należy pamiętać, że można również wyeksportować z opcją [/Export](../../build/reference/export-exports-a-function.md) konsolidatora.
