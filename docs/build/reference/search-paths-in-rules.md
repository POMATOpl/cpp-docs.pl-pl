---
description: Dowiedz się więcej o ścieżce wyszukiwania w regułach
title: Ścieżki wyszukiwania w zasadach
ms.date: 11/04/2016
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
ms.openlocfilehash: bf070fc57907b68eb458b8a5276698282ef30f9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224884"
---
# <a name="search-paths-in-rules"></a>Ścieżki wyszukiwania w zasadach

```
{frompath}.fromext{topath}.toext:
   commands
```

## <a name="remarks"></a>Uwagi

Reguła wnioskowania ma zastosowanie do zależności tylko wtedy, gdy ścieżki określone w zależności są dokładnie zgodne z ścieżkami reguł wnioskowania. Określ katalog zależny w *frompath* i katalog docelowy w *topath*; spacje nie są dozwolone. Określ tylko jedną ścieżkę dla każdego rozszerzenia. Ścieżka do jednego rozszerzenia wymaga ścieżki w drugiej. Aby określić bieżący katalog, użyj kropki (.) lub pustych nawiasów klamrowych ({}). Makra mogą reprezentować *frompath* i *topath*; są one wywoływane podczas przetwarzania wstępnego.

## <a name="example"></a>Przykład

### <a name="code"></a>Kod

```
{dbi\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUDBI) $<

{ilstore\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{misc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{misc\}.c{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{msf\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{bsc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{mre\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{namesrvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{src\cvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<
```

## <a name="see-also"></a>Zobacz też

[Definiowanie reguły](defining-a-rule.md)
