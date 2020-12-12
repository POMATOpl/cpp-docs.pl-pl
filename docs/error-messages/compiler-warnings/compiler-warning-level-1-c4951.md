---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4951'
title: Ostrzeżenie kompilatora (poziom 1) C4951
ms.date: 08/27/2018
f1_keywords:
- C4951
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
ms.openlocfilehash: effb1f5af0c406de002b5c0b8522e7c58a2424a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327962"
---
# <a name="compiler-warning-level-1-c4951"></a>Ostrzeżenie kompilatora (poziom 1) C4951

> *Funkcja "Function*" została edytowana od czasu zebrania danych profilowych, dane profilu funkcji nie zostały użyte

Funkcja została edytowana w module wejściowym do [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), tak aby dane profilu były teraz nieprawidłowe. Moduł wejściowy został ponownie skompilowany po **/LTCG: PGINSTRUMENT** i ma funkcję (*funkcję*) z innym przepływem sterowania niż w module w czasie operacji **/LTCG: PGINSTRUMENT** .

To ostrzeżenie jest informacje. Aby usunąć to ostrzeżenie, uruchom polecenie **/LTCG: PGINSTRUMENT**, wykonaj ponownie wszystkie przebiegi testowe i uruchom **/LTCG: PGOPTIMIZE**.

To ostrzeżenie zostanie zastąpione błędem, jeśli użyto **/LTCG: PGOPTIMIZE** .
