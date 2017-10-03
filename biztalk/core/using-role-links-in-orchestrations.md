---
title: "オーケストレーションでロール リンクの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e3c4e4a4c3a99fb6e1962299d440717eaa8d51b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-role-links-in-orchestrations"></a>オーケストレーションでのロール リンクの使用
ロール リンクは、オーケストレーションと取引先間の対話処理を抽象化したものです。 ロール リンクを使用すると、ビジネス プロセス全体を維持したまま、取引先の解決、メッセージの内容、またはデータベースの検索結果に基づいて取引先を動的に選択できます。  
  
 たとえば、企業間取引のシナリオでは、複数の購入者、1 つの供給業者、および供給業者の商品を配送する複数の出荷業者が存在します。 購入者が注文書を送信した場合、供給業者は、パーティの解決を通じてその購入者を特定し、適切な割引率を適用することができます。 さらに、商品の配送を担当する出荷業者を、注文された商品に基づいて実行時に決定できます。 各出荷業者は独自のトランスポート プロトコルを使用している可能性がありますが、供給業者は、実行時に同一のビジネス プロセスを使用してすべての出荷業者を処理し、どの出荷業者に配送を依頼するかを決定できます。 出荷業者は、トランスポート プロトコルを更新する場合、後の段階で、たとえば、FTP から HTTP へ — 供給業者がのみを BizTalk エクスプ ローラーまたは BizTalk Server 管理コンソールを使用して、その特定の出荷業者に関連付けられている送信ポートを更新する必要があります。 オーケストレーションに格納されているビジネス プロセスを変更する必要はありません。  
  
## <a name="roles"></a>ロール  
 オーケストレーションには次の 2 つのロールがあります。  
  
-   メッセージを受信および処理する "実装" ロール。 このロールはプロバイダーとも呼ばれます。  
  
-   メッセージを送信する "使用" ロール。 このロールはコンシューマーとも呼ばれます。  
  
## <a name="role-links"></a>ロール リンク  
 ロール リンクには、コンシューマー ロールとプロバイダー ロールのいずれか、またはその両方を含めることができます。 コンシューマー ロールは、プロバイダー ロールによって提供されるサービスを使用します。 これらのロールのいずれかまたは両方を使用するロール リンクを定義する場合は、リンクしているパートナーによって補完ロールが適切に定義されていることが前提となります。  
  
 ロール リンクには、 **SourceParty** 、プロパティ、 **DestinationParty**プロパティ、およびイニシャライズ ロール。 イニシャライズ ロールは最初の通信が発生して、ロール リンクの値を設定して開始する、ロール、 **DestinationParty**プロパティです。  
  
 イニシャライズ ロールが場合、コンシューマーのメッセージを送信するため、明示的に設定する、 **DestinationParty**オーケストレーションでのプロパティ (1 回、1 回だけ)。 値を設定するためには、 **DestinationParty**で、**式**ConfirmOrder がロール リンクの名前、PartnerName と OrganizationName が、次の例のように、図形パーティのパラメーター:  
  
```  
ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
```  
  
 イニシャライズ ロールがプロバイダーの場合、メッセージの受信、 **DestinationParty**プロパティは、受信側によって自動的に初期化します。 **DestinationParty**プロバイダー自体に設定されています。 **SourceParty**プロパティは読み取り専用、およびセキュリティ識別子 (SID) 送信者のまたはパーティに関連付けられている証明書に基づいてパーティ名を解決するのには信頼されているパイプライン コンポーネントを通じて提供されます。 パイプライン コンポーネントを実行しているホストとしてマークする必要があります**信頼されている認証**です。 値を取得することができます、 **SourceParty**で、**式**次のサンプル コードを使用して図形。  
  
 `PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);`  
  
## <a name="role-link-types"></a>ロール リンクの種類  
 ロール リンクは、ロール リンクの種類のインスタンスであり、単一のロールまたは 2 つのロールで構成されます。 ロール リンクの種類を使用する場合は、次の点を考慮します。  
  
-   単一のロールで構成されるロール リンクでは、指定したポートの種類を参照できるのは、一度だけです。  
  
-   ロール リンクの種類の定義にポートの種類が含まれるので、ポートの種類のスコープは、関連するロール リンクの種類のスコープを含む必要があります。  
  
-   ビジネス アクティビティ サービス (BAS) を使用する場合は、構造化パラメーター スキーマとそれに関連付けるロール リンクの種類を、同一の BizTalk アセンブリ内で定義する必要があります。 構造化パラメーター スキーマは、ロール リンクの種類を構成する個々のロールではなく、ロール リンクの種類に関連付けられます。したがって、役割の異なる 2 つのパーティがロール リンクの種類を含むアセンブリを共有する場合は、同じ構造化パラメーター スキーマが両方のパーティに表示されます。 同じロール リンクの種類を使用する 2 つのパーティが異なるパラメーター スキーマを必要とする場合は、各パーティに対して別々のアセンブリを作成する必要があります。 同じロール リンクの種類を両方のアセンブリ内に作成する必要があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [オーケストレーションでロール リンクを作成する方法](../core/how-to-create-role-links-in-orchestrations.md)  
  
-   [ロール リンク図形を使用する方法](../core/how-to-use-the-role-link-shape.md)  
  
-   [ロール リンク ウィザードを使用する方法](../core/how-to-use-the-role-link-wizard.md)  
  
## <a name="see-also"></a>参照  
 [パーティの解決パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-party-resolution-pipeline-component.md)   
 [オーケストレーションでポートを使用します。](../core/using-ports-in-orchestrations.md)