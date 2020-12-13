---
description: 'Dowiedz się więcej o: błąd kompilatora C3859'
title: Błąd kompilatora C3859
ms.date: 03/08/2019
f1_keywords:
- C3859
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
ms.openlocfilehash: 25c05425072cda6924d90f08c9aeff7446a4e85b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336108"
---
# <a name="compiler-error-c3859"></a>Błąd kompilatora C3859

> Przekroczono zakres pamięci wirtualnej dla PCH; Skompiluj ponownie z opcją wiersza polecenia "-zm *wartość*" lub większą

Pamięć wirtualna przypisana do prekompilowanego nagłówka jest za mała dla ilości danych, które kompilator próbuje umieścić w tym pliku. Począwszy od programu Visual Studio 2015 zalecenie **/zm** ma znaczenie tylko w przypadku korzystania z `#pragma hdrstop` dyrektywy. W innych przypadkach jest to błąd fałszywe, który wskazuje na problemy z użyciem pamięci wirtualnej systemu Windows.

Jeśli prekompilowany nagłówek używa `#pragma hdrstop` dyrektywy, Użyj flagi kompilatora **/zm** w celu określenia większej wartości prekompilowanego pliku nagłówkowego. W przeciwnym razie Rozważ zmniejszenie liczby równoległych procesów kompilacji w kompilacji. Aby uzyskać więcej informacji, zobacz [/zm (Określ limit alokacji pamięci prekompilowanego nagłówka)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).
