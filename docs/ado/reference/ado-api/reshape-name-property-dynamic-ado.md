---
title: "Reshape Name Property-Dynamic (ADO) | Microsoft Docs"
ms.prod: "sql-non-specified"
ms.technology:
  - "drivers"
ms.custom: ""
ms.date: "01/19/2017"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
apitype: "COM"
helpviewer_keywords: 
  - "Reshape Name property [ADO]"
ms.assetid: 690229d1-46cc-42e6-a57d-4438251fe248
caps.latest.revision: 13
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
---
# Reshape Name Property-Dynamic (ADO)
Specifies a name for the [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) object.  
  
## Return Values  
 Returns a **String** value that is the name of the **Recordset**.  
  
## Remarks  
 Names persist for the duration of the connection or until the **Recordset** is closed.  
  
 The **Reshape Name** property is primarily intended for use with the re-shaping feature of the [Microsoft Data Shaping Service for OLE DB](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) service provider. Names must be unique to participate in re-shaping.  
  
 This property is read-only, but can be set indirectly when a **Recordset** is created. For example, if a clause of a Shape command creates a **Recordset** and gives it an alias name by using the **AS** keyword, the alias is assigned to the **Reshape Name** property. If no alias is declared, the **Reshape Name** property is assigned a unique name generated by the data shaping service. If the alias name is the same as the name of an existing **Recordset**, neither **Recordset** can be reshaped until one of them is released. The default behavior can be changed by setting a unique name in the [Reshape Name](../../../ado/reference/ado-api/reshape-name-property-dynamic-ado.md) property on the ADO connection to **True**. Setting this property gives the data shaping service permission to change the user assigned name, if necessary, to ensure uniqueness. For more information about reshaping, see [Microsoft Data Shaping Service for OLE DB (ADO Service Provider)](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md).  
  
 Use the **Reshape Name** property when you want to refer to a **Recordset** in a Shape command, or when you do not know the name because it was generated by the Data Shaping Service. In that case, you could generate a SHAPE command by concatenating the command around the string returned by the **Reshape Name** property.  
  
 **Reshape Name** is a dynamic property appended to the **Recordset** object's [Properties](../../../ado/reference/ado-api/properties-collection-ado.md) collection when the [CursorLocation](../../../ado/reference/ado-api/cursorlocation-property-ado.md) property is set to **adUseClient**.  
  
## Applies To  
 [Recordset Object (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## See Also  
 [Microsoft Data Shaping Service for OLE DB (ADO Service Provider)](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md)   
 [Shape Commands in General](../../../ado/guide/data/shape-commands-in-general.md)   
 [Recordset Object (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)