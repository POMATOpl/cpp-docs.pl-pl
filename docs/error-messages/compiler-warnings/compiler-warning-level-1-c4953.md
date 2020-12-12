---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4953'
title: Ostrzeżenie kompilatora (poziom 1) C4953
ms.date: 08/27/2018
f1_keywords:
- C4953
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
ms.openlocfilehash: 1f10f757297bd4b0e71ec5246024a3ce7a313689
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327941"
---
# <a name="compiler-warning-level-1-c4953"></a>Ostrzeżenie kompilatora (poziom 1) C4953

> *Funkcja "Function*" została edytowana od czasu zebrania danych profilowych, dane profilowe nie są używane

W przypadku korzystania z [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)Kompilator wykrył Moduł wejściowy, który został ponownie skompilowany po `/LTCG:PGINSTRUMENT` i ma funkcję (*funkcję*), która została poddana edycji i w którym istniejące uruchomienia testów znalazły funkcję jako kandydat do wykreślania. Jednak w wyniku ponownego kompilowania modułu funkcja nie będzie już kandydatem do wykreślania.

To ostrzeżenie jest informacje. Aby usunąć to ostrzeżenie, uruchom `/LTCG:PGINSTRUMENT` polecenie, wykonaj ponownie wszystkie przebiegi testowe i uruchom polecenie `/LTCG:PGOPTIMIZE` .

To ostrzeżenie zostanie zastąpione błędem, jeśli `/LTCG:PGOPTIMIZE` był używany.
