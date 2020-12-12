---
description: Dowiedz się więcej o strukturze CCreateContext
title: CCreateContext, struktura
ms.date: 11/04/2016
f1_keywords:
- CCreateContext
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
ms.openlocfilehash: b0d8c3a38d4d6ce9ee6130092ea6b27a50ed15e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220464"
---
# <a name="ccreatecontext-structure"></a>CCreateContext, struktura

`CCreateContext`Struktura używa struktury podczas tworzenia okien ramowych i widoków, które są skojarzone z dokumentem.

## <a name="syntax"></a>Składnia

```
struct CCreateContext
```

## <a name="remarks"></a>Uwagi

`CCreateContext` jest strukturą i nie ma klasy bazowej.

Po utworzeniu okna wartości w tej strukturze zawierają informacje używane do łączenia składników dokumentu z widokiem jego danych. Należy używać tylko w `CCreateContext` przypadku przesłaniania części procesu tworzenia.

`CCreateContext`Struktura zawiera wskaźniki do dokumentu, okna ramki, widoku i szablonu dokumentu. Zawiera również wskaźnik do obiektu `CRuntimeClass` , który identyfikuje typ widoku do utworzenia. Informacje o klasie uruchomieniowej i wskaźniku bieżącego dokumentu są używane do dynamicznego tworzenia nowego widoku. W poniższej tabeli przedstawiono sposób i czas `CCreateContext` użycia każdego elementu członkowskiego:

|Członek|Typ|Do czego służy|
|------------|----------|--------------------|
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` nowego widoku do utworzenia.|
|`m_pCurrentDoc`|`CDocument*`|Istniejący dokument, który ma zostać skojarzony z nowym widokiem.|
|`m_pNewDocTemplate`|`CDocTemplate*`|Szablon dokumentu skojarzony z tworzeniem nowego okna ramki MDI.|
|`m_pLastView`|`CView*`|Oryginalny widok, w którym są modelowane dodatkowe widoki, jak w przypadku tworzenia widoków okna rozdzielacza lub tworzenia drugiego widoku dokumentu.|
|`m_pCurrentFrame`|`CFrameWnd*`|Okno ramek, w którym są modelowane dodatkowe okna ramowe, jak w przypadku tworzenia drugiego okienka ramki w dokumencie.|

Gdy szablon dokumentu tworzy dokument i powiązane z nim składniki, sprawdza poprawność informacji przechowywanych w `CCreateContext` strukturze. Na przykład nie należy tworzyć widoku dla nieistniejącego dokumentu.

> [!NOTE]
> Wszystkie wskaźniki w `CCreateContext` są opcjonalne i mogą być `NULL` nieokreślone lub nieznane.

`CCreateContext` jest używany przez funkcje składowe wymienione w sekcji "Zobacz też". Zapoznaj się z opisami tych funkcji, aby uzyskać szczegółowe informacje, jeśli planujesz ich przesłonięcie.

Oto kilka ogólnych wytycznych:

- Gdy jest przenoszona jako argument dla tworzenia okna, jak w `CWnd::Create` , `CFrameWnd::Create` i `CFrameWnd::LoadFrame` , w kontekście tworzenia określa, do czego ma być połączone nowe okno. W przypadku większości okien cała struktura jest opcjonalna i `NULL` można przesłać wskaźnik.

- Dla celów funkcji składowych, takich jak `CFrameWnd::OnCreateClient` , `CCreateContext` argument jest opcjonalny.

- W przypadku funkcji Członkowskich związanych z tworzeniem widoku należy podać wystarczającą ilość informacji, aby utworzyć widok. Na przykład dla pierwszego widoku w oknie rozdzielacza należy podać informacje o klasie widoku i bieżący dokument.

Ogólnie rzecz biorąc, jeśli używasz ustawień domyślnych platformy, możesz zignorować `CCreateContext` . Jeśli podjęto próbę wykonania bardziej zaawansowanych modyfikacji, biblioteka MFC kod źródłowy lub przykładowe programy, takie jak VIEWEX. W przypadku zapomnienia wymaganego parametru potwierdzenie struktury poinformuje użytkownika o tym, co zostało zapomniane.

Aby uzyskać więcej informacji na temat `CCreateContext` , zobacz przykład MFC [VIEWEX](../../overview/visual-cpp-samples.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxext. h

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Obiektu CFrameWnd:: Create](../../mfc/reference/cframewnd-class.md#create)<br/>
[Obiektu CFrameWnd:: LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)<br/>
[Obiektu CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)<br/>
[CSplitterWnd:: Create](../../mfc/reference/csplitterwnd-class.md#create)<br/>
[CSplitterWnd:: isView](../../mfc/reference/csplitterwnd-class.md#createview)<br/>
[CWnd:: Create](../../mfc/reference/cwnd-class.md#create)
