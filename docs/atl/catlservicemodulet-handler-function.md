---
description: 'Dowiedz się więcej o: Funkcja CAtlServiceModuleT:: Handler — funkcja'
title: 'Funkcja CAtlServiceModuleT:: Handler — funkcja'
ms.date: 11/04/2016
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
ms.openlocfilehash: 934c612b6fdfd47bb9966536cc335da58fbd38c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148372"
---
# <a name="catlservicemodulethandler-function"></a>Funkcja CAtlServiceModuleT:: Handler — funkcja

`CAtlServiceModuleT::Handler` jest procedurą, którą Menedżer kontroli usług (SCM) może pobrać stan usługi i podać różne instrukcje (na przykład zatrzymywanie lub wstrzymywanie). Menedżer SCM przekazuje kod operacji w `Handler` celu wskazania, co usługa powinna wykonać. Domyślna usługa wygenerowana przez ATL obsługuje tylko instrukcje Stop. Jeśli Menedżer SCM przejdzie do instrukcji zatrzymania, usługa nakazuje menedżerowi SCM, że program zostanie zatrzymany. Następnie usługa wywołuje, `PostThreadMessage` aby ogłosić komunikat zakończenia do samego siebie. Kończy pętlę komunikatów, a usługa zostanie ostatecznie ZAMKNIĘTA.

Aby obsłużyć więcej instrukcji, należy zmienić `m_status` element członkowski danych zainicjowany w `CAtlServiceModuleT` konstruktorze. Ten element członkowski danych informuje menedżer SCM, który przycisk włączy, gdy usługa zostanie wybrana w aplikacji panelu sterowania usługi.

## <a name="see-also"></a>Zobacz też

[Usługi](../atl/atl-services.md)<br/>
[Funkcja CAtlServiceModuleT:: Handler](../atl/reference/catlservicemodulet-class.md#handler)
