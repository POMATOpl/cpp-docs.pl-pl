---
description: 'Dowiedz się więcej o programie: wstępnie zdefiniowane reguły'
title: Wstępnie zdefiniowane zasady
ms.date: 11/04/2016
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
ms.openlocfilehash: 302c649980050764d1bb2f0e9a43b785d0175a09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225833"
---
# <a name="predefined-rules"></a>Wstępnie zdefiniowane zasady

Wstępnie zdefiniowane reguły wnioskowania używają makr poleceń i opcji dostarczonych przez NMAKE.

|Reguła|Polecenie|Domyślny<br /><br /> akcja|Batch<br /><br /> Reguła|NMAKE platformy działa na|
|----------|-------------|------------------------|--------------------|----------------------------|
|.asm.exe|$ (AS) $ (AFLAGS) $<|< ml $|nie|x86|
|. asm. obj|$ (AS) $ (AFLAGS)/c $<|ml/c $<|tak|x86|
|.asm.exe|$ (AS) $ (AFLAGS) $<|ML64 $<|nie|x64|
|. asm. obj|$ (AS) $ (AFLAGS)/c $<|ML64/c $<|tak|x64|
|.c.exe|$ (CC) $ (CFLAGS) $<|CL $<|nie|all|
|. c. obj|$ (CC) $ (CFLAGS)/c $<|cl/c $<|tak|all|
|.cc.exe|$ (CC) $ (CFLAGS) $<|CL $<|nie|all|
|. DW. obj|$ (CC) $ (CFLAGS)/c $<|cl/c $<|tak|all|
|.cpp.exe|$ (CPP) $ (CPPFLAGS) $<|CL $<|nie|all|
|. cpp. obj|$ (CPP) $ (CPPFLAGS)/c $<|cl/c $<|tak|all|
|.cxx.exe|$ (CXX) $ (CXXFLAGS) $<|CL $<|nie|all|
|. cxx. obj|$ (CXX) $ (CXXFLAGS)/c $<|cl/c $<|tak|all|
|. rc. res|$ (RC) $ (RFLAGS)/r $<|RC/r $<|nie|all|

## <a name="see-also"></a>Zobacz też

[Zasady wnioskowania](inference-rules.md)
