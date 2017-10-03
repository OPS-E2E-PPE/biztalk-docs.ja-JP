---
title: "インターセプタ EventSource 要素 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d78846c1-3984-43af-a13f-9d5c0a66d3b5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b5cd6b2e872f689988f3d10d18df002f66d6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interceptor-eventsource-element"></a>インターセプタ EventSource 要素
**EventSource**要素が 1 つ以上のインターセプター構成ファイルに表示されるイベントのソースに関する情報を提供します。 イベント ソース名だけでなく、ソースのテクノロジとマニフェストを指定する必要があります。  
  
## <a name="format"></a>Format  
 `EventSource` 要素には 3 つの属性があり、含まれているスキーマに応じて子要素がある場合とない場合があります。 たとえば、WCF スキーマである WcfInterceptorConfiguration.xsd には、`NamespaceMapping` 要素が用意されています。  
  
### <a name="attributes"></a>属性  
  
|属性名|Description|  
|--------------------|-----------------|  
|名前|イベント ソースの名前。 この名前は使用**OnEvent**エントリをソースを参照してください。|  
|テクノロジ|マニフェストで指定されたイベント ソースをホストするテクノロジの種類。 Windows Workflow Foundation には "WF"、Windows Communication Framework には "WCF" を使用します。|  
|Manifest|イベント ソースとして使用する種類のアセンブリ修飾クラス名。 たとえば、IPv4 アドレスの場合、「 `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`<br /><br /> 公開キー トークンがない場合は、`PublicKeyToken=null` を使用します。|  
  
## <a name="example"></a>例  
 次の例には 2 つ**EventSource**要素、1 つのターゲットとなる WF および WCF が 1 つです。  
  
```  
<!-- WF -->  
<ic:EventSource Name="OrderWorkflow" Technology="WF" Manifest="SimpleWorkflow.OrderWorkflow, SimpleWorkflow, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
<!-- WCF -->  
<ic:EventSource Name="PurchaseService" Technology="WCF" Manifest="Service.IProcessPOContract, DuplexService, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
```