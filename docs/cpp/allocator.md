---
description: 'Dowiedz się więcej na temat: `allocator`'
title: allocator
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: 20ca879259c49f01f5283a867b4e562cfddcc058
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288272"
---
# `allocator`

**Specyficzne dla firmy Microsoft**

**`allocator`** Specyfikator deklaracji można zastosować do funkcji niestandardowej alokacji pamięci, aby udostępnić alokacje za pośrednictwem śledzenia zdarzeń dla systemu Windows (ETW).

## <a name="syntax"></a>Składnia

> **`__declspec(allocator)`**

## <a name="remarks"></a>Uwagi

Profiler pamięci natywnej w programie Visual Studio działa przez zbieranie danych zdarzeń ETW alokacji emitowanych przez środowisko uruchomieniowe. Przydziały w CRT i Windows SDK zostały opatrzone adnotacją na poziomie źródła, aby można było przechwytywać ich dane alokacji. W przypadku pisania własnych przydziałów, wszystkie funkcje, które zwracają wskaźnik do nowo przydzieloną pamięci sterty, mogą być dekoracyjne `__declspec(allocator)` , jak pokazano w tym przykładzie dla elementu malloc:

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

Aby uzyskać więcej informacji, zobacz [miary użycie pamięci w Visual Studio](/visualstudio/profiling/memory-usage) i [niestandardowe zdarzenia sterty ETW](/visualstudio/profiling/custom-native-etw-heap-events).

**ZAKOŃCZENIE określonych przez firmę Microsoft**
