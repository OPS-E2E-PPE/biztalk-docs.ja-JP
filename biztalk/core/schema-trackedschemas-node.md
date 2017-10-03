---
title: "Schema (TrackedSchemas ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Schema node
ms.assetid: a503aad6-07f8-4650-a214-4d2f6650cb80
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5376c505332ed05507169c1db2dc54ec4e7bdfe6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="schema-trackedschemas-node"></a>Schema (TrackedSchemas ノード)
バインド ファイルの TrackedSchemas ノードの Schema ノードでは、バインド ファイルと共にエクスポートされるサービスにバインドされるスキーマを記述します。  
  
## <a name="nodes-in-the-schema-node"></a>Schema ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|FullName|属性|xs:string|スキーマの完全な名前を指定します。|任意|既定値: 空|  
|AssemblyQualifiedName|属性|xs:string|スキーマを含むアセンブリの修飾名を指定します。|任意|既定値: 空|  
|AlwaysTrackAllProperties|属性|xs:boolean|指定したアセンブリのすべてのプロパティを追跡するかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**をすべてのプロパティを追跡するには、それ以外の場合は、設定**false**です。|  
|Description|属性|xs:string|スキーマの説明を指定します。|任意|既定値: 空|  
|[TrackedPropertyNames (Schema ノード)](../core/trackedpropertynames-schema-node.md)|レコード|ArrayOfString (ComplexType)|追跡するプロパティを指定する要素のコンテナーです。|任意|既定値: なし|