---
title: インターセプター EventSource 要素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d78846c1-3984-43af-a13f-9d5c0a66d3b5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 001dfe8c2e4fe09b71bcdd8c053f59938be76cc4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382020"
---
# <a name="interceptor-eventsource-element"></a>インターセプタ EventSource 要素
**EventSource**要素が 1 つ以上のインターセプター構成ファイルに表示されるイベントのソースに関する情報を提供します。 イベント ソース名だけでなく、テクノロジと、ソース マニフェストを指定する必要があります。  
  
## <a name="format"></a>形式  
 `EventSource`要素が 3 つの属性と可能性がありますまたはスキーマが含まれていますに応じて子要素がない可能性があります。 たとえば、WCF スキーマ WcfInterceptorConfiguration.xsd 提供の`NamespaceMapping`要素。  
  
### <a name="attributes"></a>属性  
  
|属性名|説明|  
|--------------------|-----------------|  
|名前|このイベント ソースの名前です。 この名前を使って**OnEvent**エントリをソースを参照してください。|  
|テクノロジ|マニフェストで指定されたイベント ソースをホストしているテクノロジの種類。 Windows Communication Framework for Windows Workflow Foundation と"WCF"を"WF"を使用します。|  
|マニフェスト|イベント ソースとして使用する型のアセンブリ修飾クラス名。 例を次に示します。 `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`<br /><br /> 使用して、公開キー トークンがない、`PublicKeyToken=null`します。|  
  
## <a name="example"></a>例  
 次の例には 2 つ**EventSource**要素、1 つのターゲットとなる WF と WCF が 1 つ。  
  
```  
<!-- WF -->  
<ic:EventSource Name="OrderWorkflow" Technology="WF" Manifest="SimpleWorkflow.OrderWorkflow, SimpleWorkflow, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
<!-- WCF -->  
<ic:EventSource Name="PurchaseService" Technology="WCF" Manifest="Service.IProcessPOContract, DuplexService, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
```