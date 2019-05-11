---
title: BizTalk Server チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, getting started
- getting started, tutorials
ms.assetid: 58019f98-e91a-4705-b689-c269174d6bae
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66b3aad058d6d1ecbc40a62de5b73eab8aea43ec
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530388"
---
# <a name="biztalk-server-tutorials"></a>BizTalk Server チュートリアル
使用する方法についてのチュートリアル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。

BizTalk Server チュートリアルには、新しいユーザーのコンパイルされた作成、テストが容易な統合ソリューションのさまざまな BizTalk ツールを使用して、エクスペリエンスを提供する単純なシナリオが含まれます。 高度なユーザー、または BizTalk ソリューションを設計する場合にユーザーは、次を参照してください。[ビジネス ソリューションのシナリオ](../core/scenarios-for-business-solutions.md)します。  
  
## <a name="enterprise-application-integration"></a>エンタープライズ アプリケーション統合
  
[チュートリアル: エンタープライズ アプリケーション統合](../core/tutorial-1-enterprise-application-integration.md) 

倉庫から在庫補充要求メッセージを受信し、要求メッセージを評価する BizTalk ソリューションを実装します。 ソリューションは、要求を拒否する場合は、倉庫に拒否メッセージを送信します。 ソリューションが要求を承認した場合は、エンタープライズ リソース プランニング (ERP) システムにメッセージが転送します。  

## <a name="create-a-hybrid-application"></a>ハイブリッド アプリケーションを作成します。
[チュートリアル: BizTalk Server を使用してハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)  

EDI を使用してメッセージを受信する Service Bus の受信確認を生成するエンド ツー エンド アプリケーションを設定して、SQL にデータを挿入します。 

## <a name="invoke-a-rest-interface"></a>REST インターフェイスを呼び出し
[チュートリアル: BizTalk Server を使用して REST インターフェイスの呼び出し](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)  

REST の URL を使用し、応答メッセージを送信する Wcf-webhttp アダプターを使用します。 

## <a name="integrate-biztalk-with-salesforce"></a>Salesforce での BizTalk を統合します。
[チュートリアル: BizTalk Server と Salesforce の統合](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)  

Salesforce システムで営業案件が作成されるたびに通知を受け取るその他のダウン ストリーム システムがそのデータを選択し、関連するその他のプロセスを開始できるように、BizTalk Server などのオンプレミス システムが Northwind に求めています。 

## <a name="process-json-messages"></a>JSON メッセージの処理
[BizTalk Server を使用して JSON メッセージの処理](../core/processing-json-messages-using-biztalk-server.md)  

JSON 注文書を受信する BizTalk アプリケーションを設定します。 受信パイプラインでは、JSON デコーダー コンポーネントは、XML メッセージに JSON メッセージを変換します。 次に、マップを使用して XML 注文書を XML 請求書に変換します。 送信パイプラインでは、JSON 請求書では、XML 請求書に変換する JSON エンコーダーを使用し、メッセージを送信します。

## <a name="edi-interface-developer"></a>EDI インターフェイス開発
  [チュートリアル: EDI インターフェイス開発チュートリアル](../core/tutorial-2-edi-interface-developer-tutorial.md)
  
取引先は ANSI X12 を使用して発注を送信します 4010 850 トランザクション セット (850 メッセージ)。 内部の順序のシステム プロセスは発注書です。

850 メッセージの間のインターフェイスの設計を担当するインターフェイスの開発者としては、取引先パートナーと、会社の内部の注文システムから受信します。 取引先には、送信 850 メッセージごとの機能確認 (997) が必要です。


## <a name="as2"></a>AS2  
[チュートリアル: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)

受け取り、HTTP トランスポートを介して EDIINT/AS2 でエンコードされたメッセージを送信します。 ソリューションを設定します。    


## <a name="do-more"></a>さらに活用します。  
 BizTalk Server の概念とアーキテクチャの詳細については、次のことを検討してください。  
  
[開始するには](../core/getting-started-with-biztalk-server.md)
  
[計画して、BizTalk Server ソリューションの設計](../core/plan-and-architect-your-biztalk-server-solution.md)