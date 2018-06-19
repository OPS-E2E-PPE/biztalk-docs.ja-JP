---
title: BizTalk Server チュートリアル |Microsoft ドキュメント
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
ms.openlocfilehash: f13a5d74d0957a208600653823e7604680296f4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232074"
---
# <a name="biztalk-server-tutorials"></a>BizTalk Server チュートリアル
使用する方法を説明するチュートリアル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。

BizTalk Server チュートリアルでは簡単なシナリオを用意しています。初めて BizTalk Server を使用する場合でも、さまざまな BizTalk ツールの使用方法を習得しながら、コンパイルされたテスト可能な統合ソリューションを作成する方法を学習できます。 高度なユーザー、または BizTalk ソリューションの設計は、ユーザーは、次を参照してください。[ビジネス ソリューションのシナリオ](../core/scenarios-for-business-solutions.md)です。  
  
## <a name="enterprise-application-integration"></a>エンタープライズ アプリケーション統合
  
[チュートリアル: エンタープライズ アプリケーション統合](../core/tutorial-1-enterprise-application-integration.md) 

倉庫から在庫補充要求メッセージを受信し、要求メッセージを評価する BizTalk ソリューションを実装します。 ソリューションは、要求を拒否する場合は、倉庫に拒否メッセージを送信します。 ソリューションでは、要求を承認する場合は、エンタープライズ リソース プランニング (ERP) システムにメッセージが転送されます。  

## <a name="create-a-hybrid-application"></a>ハイブリッド アプリケーションを作成します。
[チュートリアル: BizTalk Server を使用してハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)  

EDI を使用してメッセージを受信するサービス バスの受信確認を生成するエンド ツー エンド アプリケーションを設定し、SQL にデータを挿入します。 

## <a name="invoke-a-rest-interface"></a>REST インターフェイスを呼び出します
[チュートリアル: BizTalk Server を使用して REST インターフェイスの呼び出し](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)  

REST の URL を使用し、応答メッセージを送信する Wcf-webhttp アダプターを使用します。 

## <a name="integrate-biztalk-with-salesforce"></a>Salesforce と BizTalk を統合します。
[チュートリアル: BizTalk Server の Salesforce との統合](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)  

Salesforce システムでは、営業案件を作成するたびに、Northwind には、通知を受ける他の下流システムがそのデータを取得したり、他の関連するプロセスを開始できるように、BizTalk Server などの内部設置型システムが希望しています。 

## <a name="process-json-messages"></a>JSON メッセージの処理
[BizTalk Server を使用して JSON メッセージの処理](../core/processing-json-messages-using-biztalk-server.md)  

JSON 注文書を受信する BizTalk アプリケーションを設定します。 受信パイプラインでは、JSON デコーダー コンポーネントは、JSON メッセージを XML メッセージを変換します。 次に、マップを使用して XML 注文を XML 請求書に変換します。 送信パイプラインは、JSON 請求書では、XML 請求書に変換する JSON エンコーダーを使用し、メッセージを送信します。

## <a name="edi-interface-developer"></a>EDI インターフェイス開発
  [チュートリアル: EDI インターフェイス開発チュートリアル](../core/tutorial-2-edi-interface-developer-tutorial.md)
  
取引先は ANSI X12 を使用して発注書送信 4010 850 トランザクション セット (850 メッセージ)。 内部の注文システム プロセスは発注書です。

インターフェイス開発者 850 メッセージの間のインターフェイスを設計するため、としては、取引先と、会社の内部の注文システムから表示されます。 取引先は、送信する 850 メッセージごとに機能確認 (997) を要求します。


## <a name="as2"></a>AS2  
[チュートリアル: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)

受信および HTTP トランスポートを介して EDIINT/AS2 でエンコードされたメッセージを送信するソリューションを設定します。    


## <a name="do-more"></a>複数の操作を行います  
 BizTalk Server の概念とアーキテクチャの詳細については、次のことを検討してください。  
  
[開始するには](../core/getting-started-with-biztalk-server.md)
  
[計画し、BizTalk Server ソリューションの設計](../core/plan-and-architect-your-biztalk-server-solution.md)