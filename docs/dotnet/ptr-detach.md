---
title: PTR::detach | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ptr.Detach
- msclr.com.ptr.Detach
- ptr::Detach
- msclr::com::ptr::Detach
dev_langs: C++
helpviewer_keywords: ptr::Detach
ms.assetid: 23370c8a-8f79-4880-9fa1-46e110c1a92c
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bf50fa11677ea8d93ce557f94015030e8b16331e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="ptrdetach"></a>ptr::Detach
Zrezygnuje prawo własności obiektu modelu COM, zwracany jest wskaźnik do obiektu.  
  
## <a name="syntax"></a>Składnia  
  
```  
_interface_type * Detach();  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Wskaźnik do obiektu COM.  
  
 Jeśli obiekt nie jest właścicielem, zwracana jest wartość NULL.  
  
## <a name="exceptions"></a>Wyjątki  
 Wewnętrznie `QueryInterface` wywołano należących do obiektu COM i wszelkich błędów `HRESULT` jest konwertowana na wyjątek przez <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.  
  
## <a name="remarks"></a>Uwagi  
 `Detach`najpierw dodaje odwołanie do obiektu modelu COM w imieniu wywołującego, a następnie zwalnia wszystkie odwołania do `com::ptr`.  Obiekt wywołujący musi zwolnić ostatecznie zwrócony obiekt do zniszczenia.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie implementuje klasy CLR, która używa `com::ptr` opakowywać jego prywatnego elementu członkowskiego `IXMLDOMDocument` obiektu.  `DetachDocument` Wywołania funkcji Członkowskich `Detach` zrezygnować prawo własności obiektu modelu COM i zwraca wskaźnik do obiektu wywołującego.  
  
```  
// comptr_detach.cpp  
// compile with: /clr /link msxml2.lib  
#include <msxml2.h>  
#include <msclr\com\ptr.h>  
  
#import <msxml3.dll> raw_interfaces_only  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
using namespace msclr;  
  
// a ref class that uses a com::ptr to contain an   
// IXMLDOMDocument object  
ref class XmlDocument {  
public:  
   // construct the internal com::ptr with a null interface  
   // and use CreateInstance to fill it  
   XmlDocument(String^ progid) {  
      m_ptrDoc.CreateInstance(progid);     
   }  
  
   // detach the COM object and return it  
   // this releases the internal reference to the object  
   IXMLDOMDocument* DetachDocument() {  
      return m_ptrDoc.Detach();  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// unmanaged function that loads XML into a raw XML DOM Document object  
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {  
   HRESULT hr = S_OK;  
   VARIANT_BOOL bSuccess;  
   hr = pDoc->loadXML(bstrXml, &bSuccess);  
   if (S_OK == hr && !bSuccess) {  
      hr = E_FAIL;  
   }  
   return hr;  
}  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   IXMLDOMDocument* pDoc = NULL;  
   BSTR bstrXml = NULL;  
  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      bstrXml = ::SysAllocString(L"<word>persnickety</word>");  
      if (NULL == bstrXml) {  
         throw gcnew OutOfMemoryException("bstrXml");  
      }  
      // detach the document object from the ref class  
      pDoc = doc.DetachDocument();  
      // use unmanaged function and raw object to load xml  
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));  
      // release document object as the ref class no longer owns it  
      pDoc->Release();  
      pDoc = NULL;  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
   finally {  
      if (NULL != pDoc) {  
         pDoc->Release();  
      }  
  
   }  
}  
```  
  
## <a name="requirements"></a>Wymagania  
 **Plik nagłówka** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>Zobacz też  
 [elementy członkowskie PTR](../dotnet/ptr-members.md)   
 [PTR::Release](../dotnet/ptr-release.md)   
 [ptr::Attach](../dotnet/ptr-attach.md)