---
description: 'Dowiedz się więcej na temat: błąd krytyczny CVTRES od CVT1100'
title: Błąd krytyczny CVTRES CVT1100
ms.date: 11/04/2016
f1_keywords:
- CVT1100
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
ms.openlocfilehash: e54a3aeaf8b0b7955ab7e9cb7558c97a57fc95e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119739"
---
# <a name="cvtres-fatal-error-cvt1100"></a>Błąd krytyczny CVTRES CVT1100

zduplikowany zasób — typ: wpisz, Name: Name, language: language, flags: flags, size: size

Podany zasób został określony więcej niż raz.

Ten błąd może wystąpić, jeśli konsolidator tworzy bibliotekę typów i nie określono [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) , a zasób w projekcie używa już 1. W takim przypadku należy określić/TLBID i określić inną liczbę do 65535.
