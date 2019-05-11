---
title: Schema (TrackedSchemas ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Schema node
ms.assetid: a503aad6-07f8-4650-a214-4d2f6650cb80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe27ed2ce631fe27cb34ec44bb792349737dbe01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396887"
---
# <a name="schema-trackedschemas-node"></a>Schema (TrackedSchemas ノード)
バインド ファイルの TrackedSchemas ノードのスキーマのノードは、バインド ファイルと共にエクスポートされるサービスにバインドされるスキーマについて説明します。  
  
## <a name="nodes-in-the-schema-node"></a>ノード内のスキーマ ノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|FullName|属性|xs:string|スキーマの完全な名前を指定します。|任意|既定値: 空|  
|AssemblyQualifiedName|属性|xs:string|このスキーマを含むアセンブリの修飾名を指定します。|任意|既定値: 空|  
|AlwaysTrackAllProperties|属性|xs:boolean|指定されたアセンブリのすべてのプロパティを追跡するかどうかを指定します。|必須|既定値: なし<br /><br /> 設定**true**をすべてのプロパティを追跡するには、それ以外の場合は、設定**false**します。|  
|説明|属性|xs:string|スキーマの説明を指定します。|任意|既定値: 空|  
|[TrackedPropertyNames (Schema ノード)](../core/trackedpropertynames-schema-node.md)|レコード|(ComplexType)|追跡対象プロパティを指定する要素のコンテナーです。|任意|既定値: なし|