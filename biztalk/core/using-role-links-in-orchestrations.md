---
title: オーケストレーションでロール リンクの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- role links
- roles, links
- roles
- roles, about roles
- role links, about role links
- role links, properties
- role links, initializing
ms.assetid: 0cf85544-12c9-4541-8925-61a6e946cce0
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3508252cd77f002d635958f0f2bdc0202ace2d56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396555"
---
# <a name="using-role-links-in-orchestrations"></a>オーケストレーションでロール リンクの使用
ロール リンクは、オーケストレーションと取引先パートナーとの間の相互作用の抽象化の形式です。 ロール リンクを使用して、取引先との対話には取引先パートナーの解決、メッセージの内容、またはデータベースの検索結果のビジネス プロセス全体をそのまま維持しながらに基づいて動的に選択できます。  
  
 たとえば、企業間取引シナリオでは複数の購入者、1 つの納入業者、およびサプライヤーの出荷業者を複数。 購入者は、注文書を業者に送信するときに、購入者は、注文書を送信し、適切な割引を適用するパーティの解決を供給します。 供給業者は、出荷業者は、配信を担当する実行時にさらに、注文された商品をに基づいて決定します。 各出荷業者には、独自のトランスポート プロトコルがありますが、サプライヤーことができます、同じビジネス プロセス実行時に使用をすべての出荷業者を処理し、対話する機関を決定します。 出荷業者は、トランスポート プロトコルを更新する場合、後の段階で、たとえば、FTP HTTP からから-業者がのみ BizTalk エクスプローラまたは BizTalk Server 管理コンソールを使用して、その出荷業者に関連付けられている送信ポートを更新する必要があります。 供給業者は、オーケストレーションが存在する、そのビジネス プロセスを変更する必要はありません。  
  
## <a name="roles"></a>ロール  
 オーケストレーションでは、2 つのロールがあります。  
  
-   メッセージ受信して処理する「実装」ロール。 このロールは、プロバイダーでとも呼ばれます。  
  
-   メッセージを送信する「使用」ロール。 この役割は、コンシューマーとも呼ばれます。  
  
## <a name="role-links"></a>ロール リンク  
 ロール リンクには、コンシューマーまたはプロバイダー ロール、またはそれぞれの 1 つを含めることができます。 コンシューマー ロールは、プロバイダーの役割によって提供されるサービスを使用します。 これらのロールの一方または両方のロール リンクを定義するときに、リンクしているパートナーによって補完ロールが実行されたことと見なされます。  
  
 ロール リンクには、 **SourceParty**プロパティ、 **DestinationParty**プロパティ、およびイニシャライズ ロール。 イニシャライズ ロールは、最初の通信が発生すると、およびそのため、ロール リンクの値を設定して開始ロール、 **DestinationParty**プロパティ。  
  
 明示的に設定イニシャライズ ロールでは、メッセージを送信するため、コンシューマーが場合、 **DestinationParty**オーケストレーション内のプロパティ (1 回、1 回だけ)。 これを行うには、値を設定、 **DestinationParty**で、**式**ConfirmOrder がロール リンクの名前であり、PartnerName と OrganizationName が、次の例のように、図形パーティのパラメーター:  
  
```  
ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
```  
  
 イニシャライズ ロールがプロバイダーの場合、メッセージの受信、 **DestinationParty**プロパティは、受信側によって自動的に初期化します。 **DestinationParty**プロバイダー自体に設定されています。 **SourceParty**プロパティは読み取り専用、およびセキュリティ識別子 (SID) 送信者のまたはパーティに関連付けられている証明書に基づいてパーティ名を解決するのには信頼されているパイプライン コンポーネントを通じて提供されます。 パイプライン コンポーネントを実行しているホストとしてマークする必要があります**信頼されている認証**です。 値を取得することができます、 **SourceParty**で、**式**次のサンプル コードを使用して図形。  
  
 `PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);`  
  
## <a name="role-link-types"></a>ロール リンクの種類  
 ロール リンクは、1 つまたは 2 つのいずれかのロールで構成されるロール リンクの種類のインスタンスです。 ロール リンクの種類を使用する場合は、次を考慮してください。  
  
-   1 つのロール リンクの種類内の特定のポートの型に 1 回だけ参照することができます。  
  
-   ロール リンクの種類の定義には、ポートの種類が含まれているため、それを使用するロール リンクの種類のポートの種類のスコープを網羅する必要があります。  
  
-   ビジネス アクティビティ サービス (BAS) を使用する場合が関連付けられているロール リンクの種類と同じ BizTalk アセンブリで構造化パラメータ スキーマを定義する必要があります。 スキーマは、さまざまな役割を果たす当事者がロール リンクの種類を含むアセンブリを共有している場合、ロール リンクの種類およびそのロール リンクの種類を構成する個々 のロールではなくに関連付けであるため両方のパーティが同じ構造化パラメータに表示されます。スキーマです。 2 つのパーティで同じロール リンクの種類を使用している場合、異なるパラメーター スキーマがあります、各パーティの別のアセンブリを作成する必要があります。 ロール リンクの種類は、各アセンブリ内で重複する必要があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [オーケストレーションでロール リンクを作成する方法](../core/how-to-create-role-links-in-orchestrations.md)  
  
-   [ロール リンク図形を使用する方法](../core/how-to-use-the-role-link-shape.md)  
  
-   [ロール リンク ウィザードを使用する方法](../core/how-to-use-the-role-link-wizard.md)  
  
## <a name="see-also"></a>参照  
 [パーティの解決パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-party-resolution-pipeline-component.md)   
 [オーケストレーションでのポートの使用](../core/using-ports-in-orchestrations.md)