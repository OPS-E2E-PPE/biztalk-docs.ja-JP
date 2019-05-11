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
ms.openlocfilehash: a5509fe9ec6b4d1966af84e56ca1b1571ebc3f55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390273"
---
# <a name="continuationtoken"></a>ContinuationToken
継続トークンは、BAM インフラストラクチャ内の異種情報を関連付けるために使用されます。 次の種類のメッセージを構築するビジネス プロセスを考慮してください。  
  
- 注文書番号で識別される発注書  
  
- 販売注文番号で識別される販売注文  
  
- 出荷指示番号により識別される出荷指示  
  
  このプロセスでは、次の 3 つの重要な識別子: 注文 ID、販売注文 ID、および注文 ID の配布の購入 元の注文の有効期間中に重要なイベントを通知これらの各識別子が、直接関連付けることはできません。 注文書に関連するイベントを追跡するために、BAM 追跡インフラストラクチャが正確にイベントを関連付けるため、メッセージ間で共通の情報を識別する必要があります。  
  
## <a name="format"></a>形式  
 継続トークンは、式の要素と 1 つまたは複数の操作で構成されます。  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="remarks"></a>コメント  
 次の一般的な操作は、ContinuationToken 式では使用できません。  
  
- And  
  
- [等しい]  
  
  [WF/WCF の operations セクション ヘッダーに応じてが必要のようなグラフやその他のグラフ]  
  
## <a name="example"></a>例  
 この例では、ワークフローから、WF プロセスの継続トークンを取得を使用して`GetWorkflowProperty`します。 ここで継続トークンを確認するプロセスは、2 つまたは 3 つの式よりも多く、外部データに依存する可能性がありますので、おそらく、カスタム コードを使用して、ワークフローにおける連続性をサポートするよう、開発者が決定します。  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>ContinuationToken</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
 新しい WF または WCF アプリケーションで同様の機能を提供することができます、または、トークンが簡単に式の操作を使用して確立する場合は、追加のコードを記述する必要があります。  
  
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