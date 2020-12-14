---
description: 'Dowiedz się więcej na temat: RW4004 ostrzeżenia kompilatora zasobów'
title: Ostrzeżenie RW4004 kompilatora zasobów
ms.date: 11/04/2016
f1_keywords:
- RW4004
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
ms.openlocfilehash: 5609d49e242ba7d74025622c53c279ae1b0da854
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237000"
---
# <a name="resource-compiler-warning-rw4004"></a>Ostrzeżenie RW4004 kompilatora zasobów

Znak ASCII nie jest odpowiednikiem kodu klucza wirtualnego

Literał ciągu został użyty dla kodu klucza wirtualnego w akceleratorze typu standardowym VIRTKEY.

To ostrzeżenie pozwala kontynuować, ale należy pamiętać, że wygenerowane klucze akceleratora mogą być niezgodne z podanym ciągiem. (VIRTKEYs używają innych kodów kluczy niż akceleratory ASCII).

Gdy literały ciągu są syntaktycznie prawidłowe, można upewnić się, że odpowiedni akcelerator można uzyskać przy użyciu **VK_ \* #define** wartości w systemie Windows. h.
