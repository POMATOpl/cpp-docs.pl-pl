---
description: 'Dowiedz się więcej o: wywoływaniu skryptów'
title: Wywoływanie skryptów (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
ms.openlocfilehash: 48fc49118d93893b5cd60462fbaecfdb73d747c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152662"
---
# <a name="invoking-scripts"></a>Wywoływanie skryptów

[Użycie parametrów wymiennych (preprocesora rejestratora)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) omawia mapy wymiany i wymienia metodę **zastępowania** metody rejestratora. Rejestrator ma osiem innych metod specyficznych dla skryptów, a wszystkie są opisane w poniższej tabeli.

|Metoda|Składnia/opis|
|------------|-------------------------|
|**ResourceRegister**|**HRESULT ResourceRegister (LPCOLESTR***resFileName* **, uint** `nID` **, LPCOLESTR** `szType` **);**      <br /><br /> Rejestruje skrypt zawarty w zasobie modułu. *resFileName* wskazuje ścieżkę UNC do samego modułu. *NID* i *SZTYPE* zawierają odpowiednio identyfikator i typ zasobu.|
|**ResourceUnregister**|**HRESULT ResourceUnregister (LPCOLESTR***resFileName* **, uint** `nID` **, LPCOLESTR** `szType` **);**      <br /><br /> Wyrejestrowuje skrypt zawarty w zasobie modułu. *resFileName* wskazuje ścieżkę UNC do samego modułu. *NID* i *SZTYPE* zawierają odpowiednio identyfikator i typ zasobu.|
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);**      <br /><br /> Rejestruje skrypt zawarty w zasobie modułu. *resFileName* wskazuje ścieżkę UNC do samego modułu. *szID* i *szType* zawierają odpowiednio identyfikator i typ ciągu zasobu.|
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);**      <br /><br /> Wyrejestrowuje skrypt zawarty w zasobie modułu. *resFileName* wskazuje ścieżkę UNC do samego modułu. *szID* i *szType* zawierają odpowiednio identyfikator i typ ciągu zasobu.|
|**FileRegister**|**HRESULT FileRegister (LPCOLESTR**  *filename*  **);**<br /><br /> Rejestruje skrypt w pliku. *Nazwa pliku* jest ścieżką UNC do pliku, który zawiera skrypt zasobu (lub).|
|**FileUnregister**|**HRESULT FileUnregister (LPCOLESTR**  *filename*  **);**<br /><br /> Wyrejestrowuje skrypt z pliku. *Nazwa pliku* jest ścieżką UNC do pliku, który zawiera skrypt zasobu (lub).|
|**StringRegister**|**HRESULT StringRegister (***dane* LPCOLESTR **);**    <br /><br /> Rejestruje skrypt w ciągu. *dane* zawierają sam skrypt.|
|**StringUnregister**|**HRESULT StringUnregister (***dane* LPCOLESTR **);**    <br /><br /> Wyrejestrowuje skrypt w ciągu. *dane* zawierają sam skrypt.|

**ResourceRegisterSz** i **ResourceUnregisterSz** są podobne do **ResourceRegister** i **ResourceUnregister**, ale umożliwiają określanie identyfikatora ciągu.

Metody **FileRegister** i **FileUnregister** są przydatne, jeśli nie chcesz, aby skrypt był używany w zasobie, lub jeśli chcesz, aby skrypt był w jego własnym pliku. Metody **StringRegister** i **StringUnregister** zezwalają, aby plik. RGS był przechowywany w dynamicznie przydzielonym ciągu.

## <a name="see-also"></a>Zobacz też

[Tworzenie skryptów rejestratora](../atl/creating-registrar-scripts.md)
