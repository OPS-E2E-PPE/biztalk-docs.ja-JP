---
title: ContinuationToken |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4911fc-c6fb-4628-9177-bd723d4d8ebc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f0d36737ddd16e34ecfe4680c7660e16c99f676
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001867"
---
# <a name="continuationtoken"></a>ContinuationToken
接続トークンは、BAM インフラストラクチャ内の異種情報を関連付けるために使用されます。 次の種類のメッセージを構築するビジネス プロセスが考えられます。  
  
- 注文書番号により識別される注文書  
  
- 販売注文番号により識別される販売注文  
  
- 出荷指示番号により識別される出荷指示  
  
  このプロセスでは、次の 3 つの重要な識別子: 注文 ID、販売注文 ID、および注文 ID の配布の購入 これらの各識別子は、元の注文の有効期間において重要なイベントを示しますが、直接関連付けることはできません。 注文書に関連するイベントを追跡するには、BAM 追跡インフラストラクチャでイベントを正確に関連付けることができるようにするために、メッセージ間で共通する情報を識別する必要があります。  
  
## <a name="format"></a>[形式]  
 接続トークンは、1 つの式要素と 1 つ以上の操作で構成されます。  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="remarks"></a>コメント  
 次の一般的な演算は、ContinuationToken 式では許可されていません。  
  
- And  
  
- [等しい]  
  
  [WF/WCF の Operations セクション ヘッダーには同様のチャートおよび必要に応じたその他のチャートが必要です。]  
  
## <a name="example"></a>例  
 この例では、WF プロセスの接続トークンが、`GetWorkflowProperty` を使用してワークフローから取得されます。 ここでは、カスタム コードを使用して、ワークフローにおける連続性のサポートを提供するよう開発者が決定しています。これはおそらく、接続トークンを確認するプロセスに 2 つまたは 3 つ以上の式が含まれるため、および外部データに依存する可能性があるためです。  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>ContinuationToken</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
 新しい WF アプリケーションまたは新しい WCF アプリケーションで、同様の機能を提供することを選択する場合があります。また、式操作を使用してトークンが簡単に確立する場合、追加のコードを記述せずに済みます。  
  
 次の例を使用して、WCF プロセスの継続トークンを確立、 **XPath**の現在のメッセージからクレジット_カード番号を取得する操作と**定数**と**連結**に取得した番号を文字列"CID_"を付加する操作。  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CID_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//Purchase/Payment/CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="see-also"></a>参照  
 [インターセプター OnEvent 要素](../core/interceptor-onevent-element.md)