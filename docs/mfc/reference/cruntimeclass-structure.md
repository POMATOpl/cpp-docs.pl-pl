---
description: Dowiedz się więcej o strukturze CRuntimeClass
title: CRuntimeClass, struktura
ms.date: 11/04/2016
f1_keywords:
- CRuntimeClass
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
ms.openlocfilehash: e02732ec595026f028ad4b8f9bd3d8898a40cbc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342920"
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass, struktura

Każda klasa pochodna `CObject` jest skojarzona ze `CRuntimeClass` strukturą, której można użyć, aby uzyskać informacje o obiekcie lub jego klasie bazowej w czasie wykonywania.

## <a name="syntax"></a>Składnia

```
struct CRuntimeClass
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CRuntimeClass:: CreateObject](#createobject)|Tworzy obiekt w czasie wykonywania.|
|[CRuntimeClass:: from](#fromname)|Tworzy obiekt w czasie wykonywania przy użyciu znanej nazwy klasy.|
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|Określa, czy Klasa pochodzi od określonej klasy.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CRuntimeClass:: m_lpszClassName](#m_lpszclassname)|Nazwa klasy.|
|[CRuntimeClass:: m_nObjectSize](#m_nobjectsize)|Rozmiar obiektu w bajtach.|
|[CRuntimeClass:: m_pBaseClass](#m_pbaseclass)|Wskaźnik do `CRuntimeClass` struktury klasy bazowej.|
|[CRuntimeClass:: m_pfnCreateObject](#m_pfncreateobject)|Wskaźnik do funkcji, która dynamicznie tworzy obiekt.|
|[CRuntimeClass:: m_pfnGetBaseClass](#m_pfngetbaseclass)|Zwraca `CRuntimeClass` strukturę (dostępną tylko w przypadku połączenia dynamicznego).|
|[CRuntimeClass:: m_wSchema](#m_wschema)|Numer schematu klasy.|

## <a name="remarks"></a>Uwagi

`CRuntimeClass` jest strukturą i w związku z tym nie ma klasy bazowej.

Możliwość ustalenia klasy obiektu w czasie wykonywania jest przydatna, gdy wymagane jest dodatkowe sprawdzanie typu argumentów funkcji lub jeśli trzeba pisać kod specjalnego przeznaczenia na podstawie klasy obiektu. Informacje o klasach środowiska uruchomieniowego nie są obsługiwane bezpośrednio w języku C++.

`CRuntimeClass` zawiera informacje dotyczące powiązanego obiektu języka C++, takie jak wskaźnik do `CRuntimeClass` klasy podstawowej i nazwa klasy ASCII powiązanej klasy. Ta struktura implementuje również różne funkcje, które mogą służyć do dynamicznego tworzenia obiektów, określania typu obiektu przy użyciu znanej nazwy i ustalania, czy powiązana Klasa pochodzi od określonej klasy.

Aby uzyskać więcej informacji na temat korzystania z programu `CRuntimeClass` , zobacz artykuł [Uzyskiwanie dostępu do Run-Time informacji o klasie](../../mfc/accessing-run-time-class-information.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CRuntimeClass`

## <a name="requirements"></a>Wymagania

**Nagłówek:** AFX. h

## <a name="cruntimeclasscreateobject"></a><a name="createobject"></a> CRuntimeClass:: CreateObject

Wywołaj tę funkcję, aby dynamicznie utworzyć określoną klasę w czasie wykonywania.

```
CObject* CreateObject();

static CObject* PASCAL CreateObject(LPCSTR lpszClassName);

static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Parametry

*lpszClassName*<br/>
Znana nazwa klasy, która ma zostać utworzona.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do nowo utworzonego obiektu lub wartość NULL, jeśli nie odnaleziono nazwy klasy lub gdy jest za mało pamięci, aby utworzyć obiekt.

### <a name="remarks"></a>Uwagi

Klasy pochodne `CObject` mogą obsługiwać tworzenie dynamiczne, które jest możliwość tworzenia obiektu określonej klasy w czasie wykonywania. Klasy dokumentów, widoków i ramek, na przykład, powinny obsługiwać dynamiczne tworzenie. Aby uzyskać więcej informacji na temat tworzenia dynamicznego i `CreateObject` elementu członkowskiego, zobacz [Klasa CObject](../../mfc/using-cobject.md) i [Klasa CObject: Określanie poziomów funkcjonalności](../../mfc/specifying-levels-of-functionality.md).

### <a name="example"></a>Przykład

  Zobacz przykład dla [IsDerivedFrom](#isderivedfrom).

## <a name="cruntimeclassfromname"></a><a name="fromname"></a> CRuntimeClass:: from

Wywołaj tę funkcję, aby pobrać `CRuntimeClass` strukturę skojarzoną z znajomą nazwą.

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Parametry

*lpszClassName*<br/>
Znana nazwa klasy pochodnej `CObject` .

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do `CRuntimeClass` obiektu odpowiadający nazwie, która została przeniesiona w *lpszClassName*. Funkcja zwraca wartość NULL, jeśli nie znaleziono pasującej nazwy klasy.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

## <a name="cruntimeclassisderivedfrom"></a><a name="isderivedfrom"></a> CRuntimeClass::IsDerivedFrom

Wywołaj tę funkcję, aby określić, czy Klasa wywołująca pochodzi od klasy określonej w parametrze *pBaseClass* .

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>Parametry

*pBaseClass*<br/>
Znana nazwa klasy pochodnej `CObject` .

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli wywoływana Klasa `IsDerivedFrom` jest pochodną klasy bazowej, której `CRuntimeClass` Struktura jest określona jako parametr; w przeciwnym razie false.

### <a name="remarks"></a>Uwagi

Relacja jest określana przez "idące" z klasy składowej w łańcuchu klas pochodnych do góry. Ta funkcja zwraca wartość FALSE, jeśli nie odnaleziono dopasowania dla klasy bazowej.

> [!NOTE]
> Aby użyć `CRuntimeClass` struktury, musisz uwzględnić makro IMPLEMENT_DYNAMIC, IMPLEMENT_DYNCREATE lub IMPLEMENT_SERIAL w implementacji klasy, dla której chcesz pobrać informacje o obiekcie czasu wykonywania.

Aby uzyskać więcej informacji na temat korzystania z programu `CRuntimeClass` , zobacz artykuł [CObject Class: uzyskiwanie dostępu Run-Time informacji o klasie](../../mfc/accessing-run-time-class-information.md).

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

## <a name="cruntimeclassm_lpszclassname"></a><a name="m_lpszclassname"></a> CRuntimeClass:: m_lpszClassName

Ciąg zakończony znakiem null zawierający nazwę klasy ASCII.

### <a name="remarks"></a>Uwagi

Ta nazwa może służyć do tworzenia wystąpienia klasy przy użyciu `FromName` funkcji składowej.

### <a name="example"></a>Przykład

  Zobacz przykład dla [IsDerivedFrom](#isderivedfrom).

## <a name="cruntimeclassm_nobjectsize"></a><a name="m_nobjectsize"></a> CRuntimeClass:: m_nObjectSize

Rozmiar obiektu w bajtach.

### <a name="remarks"></a>Uwagi

Jeśli obiekt ma elementy członkowskie danych wskazujące przydzieloną pamięć, rozmiar tej pamięci nie jest uwzględniany.

### <a name="example"></a>Przykład

  Zobacz przykład dla [IsDerivedFrom](#isderivedfrom).

## <a name="cruntimeclassm_pbaseclass"></a><a name="m_pbaseclass"></a> CRuntimeClass:: m_pBaseClass

Jeśli aplikacja statycznie łączy się z MFC, ten element członkowski danych zawiera wskaźnik do `CRuntimeClass` struktury klasy bazowej.

### <a name="remarks"></a>Uwagi

Jeśli aplikacja łączy się dynamicznie z biblioteką MFC, zobacz [m_pfnGetBaseClass](#m_pfngetbaseclass).

### <a name="example"></a>Przykład

  Zobacz przykład dla [IsDerivedFrom](#isderivedfrom).

## <a name="cruntimeclassm_pfncreateobject"></a><a name="m_pfncreateobject"></a> CRuntimeClass:: m_pfnCreateObject

Wskaźnik funkcji do domyślnego konstruktora, który tworzy obiekt klasy.

### <a name="remarks"></a>Uwagi

Ten wskaźnik jest prawidłowy tylko wtedy, gdy klasa obsługuje tworzenie dynamiczne; w przeciwnym razie funkcja zwraca wartość NULL.

## <a name="cruntimeclassm_pfngetbaseclass"></a><a name="m_pfngetbaseclass"></a> CRuntimeClass:: m_pfnGetBaseClass

Jeśli aplikacja używa biblioteki MFC jako współdzielonej biblioteki DLL, ten element członkowski danych wskazuje funkcję, która zwraca `CRuntimeClass` strukturę klasy bazowej.

### <a name="remarks"></a>Uwagi

Jeśli aplikacja statycznie łączy się z biblioteką MFC, zobacz [m_pBaseClass](#m_pbaseclass).

### <a name="example"></a>Przykład

  Zobacz przykład dla [IsDerivedFrom](#isderivedfrom).

## <a name="cruntimeclassm_wschema"></a><a name="m_wschema"></a> CRuntimeClass:: m_wSchema

Numer schematu (-1 dla klas, które nie są serializowane).

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat numerów schematu, zobacz makro [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) .

### <a name="example"></a>Przykład

  Zobacz przykład dla [IsDerivedFrom](#isderivedfrom).

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[CObject:: GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
