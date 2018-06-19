---
title: サプライ チェーンのシナリオのサンプル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- supply chains, examples
- examples, supply chains
ms.assetid: 1837a2c8-b1d4-4e1f-a196-a48b13b22662
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e305021e5b1206cc46ba40c2d2c4cd098c6c6e06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211522"
---
# <a name="sample-supply-chain-scenario"></a>サンプル サプライ チェーン シナリオ
発注要求および応答メッセージの交換は、先端技術を駆使したサプライ チェーンの最も基本的なプロセスの 1 つです。 購入者が発注書を発行すると、業者は製品ライン レベル単位で注文を受けるかどうか、または注文が保留になっているかどうかを確認します。  
  
 ここでは、発注メッセージを交換する取引先 2 社のシナリオをサンプルとして使用し、統合と自動化によってプロセスが強化されるしくみについて説明します。  
  
## <a name="the-players"></a>背景説明  
 このサンプル シナリオでの購入者は大規模なハイテク装置メーカーです。 現在は EDI ベースのシステムを使用してデータの自動交換を行っています。 EDI を使用しない業者に対しては、電話、FAX、スプレッドシートを添付した電子メール、および Web アプリケーションを使用しています。 EDI を使用する業者であっても、取引先との通信をバックエンド ERP システムに統合する機能は制約されています。 EDI を介して注文と情報を受信した後で、これらの注文を ERP システムに手動で再入力する必要があります。 このような理由により、取引先に関する需要、インベントリ、購入、およびレポートを自動化することで、既存のサプライ チェーンを向上させたいと考えています。 そのためには、業者と顧客をインターネット経由で接続し、さらに既存の基幹業務 (LOB) アプリケーションを直接統合できるシステムが必要です。  
  
 販売者は、高性能 IC を取り扱う中規模の業者です。 現在電話を使用して、取引先との通信、fax、電子メールと添付[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシート、FTP、および Web アプリケーションです。 EDI は使用していません。 各取引先とのやり取りは、顧客および顧客が使用しているテクノロジのニーズに応じて異なります。 ビジネス プロセスを効率よくすることで、トランザクション コストの削減、顧客満足度の向上、競争力の強化を図りたいと考えています。  
  
## <a name="the-present-business-process"></a>現在のビジネス プロセス  
 統合ソリューションを使用しない場合のメーカーと業者の発注プロセスは、次のように機能します。  
  
1.  ハイテク装置メーカーの顧客は、Web サイトを使用して、このメーカーに発注を送信します。  
  
2.  この注文に応じて、ハイテク装置メーカーの従業員は、IC 供給業者へ送る発注要求メッセージを LOB ERP アプリケーションで作成します。  
  
3.  作成された発注要求は、メーカー社内の各関係者に回され、記録、処理、確認、および承認が行われます。 その際、ERP システム ユーザーの場合は自動的に処理されますが、そうでない場合は、電子メールに [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] スプレッドシートを添付するなど手動で処理することになります。  
  
4.  従業員が電子メールで発注要求を作成し、業者に送信します。 他の従業員も同様のプロセスを経て、他の業者と電子メール、FAX、または EDI を使用して通信します。 使用するプロセスは、部門ごとに異なります。 EDI を使用する業者の場合でも、メーカーの従業員は ERP システムから手動でメッセージを作成する必要があります。  
  
5.  業者の従業員はメッセージを受信すると、データ形式を変更して ERP システムに手動で入力します。 従業員は電子メールを使用して、要求を他の従業員に通知します。  
  
6.  他の従業員は、この要求を分析します。 必要に応じて、部品供給業者に必要な部品の通知を送信します。 業者に応じて、電話、FAX、電子メール、または FTP で通知します。  
  
7.  各従業員は部署および業者と相談した後で、発注書の各製品品目を受けるか断るかを決定し、発注を受けるかどうかの通知、または注文が保留になっていることの通知を出します。 これらのタスクは、ERP システムを使用して実行します。  
  
8.  業者の従業員は発注応答を電子メールで作成して、製品品目ごとに発注を受けるか断るかを知らせます。あるいは、発注が保留になっていることを知らせるメッセージを作成します。 業者の従業員は、メーカーに応答メッセージを送信します。 保留中の製品品目がある場合は、該当する品目の発注を受けるか断るかを知らせる別のメッセージを後で作成します。  
  
9. メーカーの従業員は、発注応答を受信します。 バックエンド ERP システムに注文を再入力します。  
  
10. 別の従業員が発注確認を分析し、発注元の顧客に送信する発注確認の応答メッセージを作成します。 この応答メッセージは電子メールで送信します。  
  
## <a name="the-rosettanet-solution"></a>RosettaNet ソリューション  
 Microsoft BizTalk Server および [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] は、発注要求と応答プロセスを自動化および標準化します。 統合システムを使用することで、手動での操作、使用する用紙の量、使用する電話と FAX の回数を最小限に抑えます。 ほとんどのプロセスは、統合されたサーバー コンピューター間で自動的に処理されます。 手動で操作を実行する必要があるときは、バックエンド ERP システムで行います。 次の図は、統合システムを示しています。  
  
 ![(& m); 60変更なし &#62;。] (../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-integrated-supply-chain-scenario.gif "RN3_Integrated_Supply_Chain_Scenario")  
  
 このシナリオでは、統合システムにより、次のようにプロセスが変わりました。  
  
-   メーカーと IC 供給業者間で行われていた手動処理は、RNIF (RosettaNet Implementation Framework) 接続によって処理されます。 つまり、メッセージの送受信、バックエンド システムへのデータのルーティング、メッセージの確認と応答はすべて自動的に行われます。 メーカーと業者の両方が [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を使用して、RNIF 接続を実装します。  
  
-   メーカー、IC 供給業者、他の取引先との間で行われていた EDI 接続が、RNIF 接続に変更されました。 これにより、統合システムはデータを取引先のバックエンド システムに自動的にルーティングできます。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を使用して RNIF 接続を実装する取引先もあれば、RosettaNet に準拠する別のソリューションを使用する取引先もあります。  
  
-   RosettaNet に準拠するソリューションを使用しない小規模なパートナーについては、Web ブラウザーからアクセスできる Web サービスを作成します。 この Web サービスは、標準の RNIF 接続を使用してメーカー側または IC 供給業者側の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムと通信します。  
  
-   メーカーと業者の間で交換されるメッセージでは、標準の RosettaNet PIP (Partner Interface Process) に準拠するスキーマを使用します。 これらのスキーマは、EDI と FTP で使用される形式を置き換えます。 すべての取引先が同じスキーマを使用します。このようにすると、メッセージ間でデータをマップする必要がありません。  
  
-   [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はスキーマに対してすべてのメッセージを自動的に検証するため、データ エラーのリスクが低下します。  
  
-   管理者は管理ソフトウェア ツールを使用して、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] サーバー上で操作することができます。 ビジネスの意思決定者は、クライアント コンピューター上で Microsoft Office ベースのアプリケーションまたはツールがホストするビジネス監視ツールを使用できます。 どちらもシステムの効率的な動作を保持するための有効なプロセスで、システムおよびビジネスがどのように実行しているかを視覚的に認識できます。  
  
### <a name="message-flow"></a>メッセージ フロー  
 ビジネス プロセスには次の手順が含まれます。  
  
1.  ハイテク装置メーカーの顧客は、Web サイトを使用して、このメーカーに発注を送信します。  
  
2.  この元の注文に応じて、メーカーの従業員は会社の受注在庫管理システムで発注要求メッセージを作成します。 この LOB アプリケーションは、Web ベースのユーザー インターフェイスを使用した ERP システムです。  
  
3.  システムは、ERP システムの固有の形式を使用して、この発注要求メッセージを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] に送信します。  
  
4.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、RosettaNet 組織で定義されている 3A4 PIP に準拠した発注要求メッセージを自動的に生成します。 この発注要求は XML 形式です。 PIP は、メッセージの内容を定義します。  
  
    > [!NOTE]
    >  3A4 PIP は、すべての発注要求および応答メッセージが同じ形式であることを確認します。 この PIP は、RosettaNet で定義されている、完全に相互接続されたメッセージング システムを形成する PIP コレクションの一部です。 たとえば、購入者は 3A4 メッセージを送信する前に、価格とアベイラビリティの要求 (PIP 3A2)、見積もりの要求 (PIP 3A1)、ショッピング カート転送 (PIP 3A3) を行うことができます。 また、発注要求を送信した後で、発注の変更 (PIP 3A8)、発注の取り消し (PIP 3A9)、発注状態の照会 (PIP 3A5)、発注状態の配信 (PIP 3A6) を行うことができます。 これらのすべてのメッセージは、RosettaNet 組織によって標準化されています。  
  
5.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、要求メッセージ (具体的には Service Content) を RNIF ヘッダーでラップします。これにより、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はインターネット経由で業者サイトの別の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] コンピュータにメッセージを送信できるようになります。 RNIF は、パートナーがインターネット経由でメッセージを交換する方法を定義します。  
  
6.  メーカーの [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムは、IC 供給業者の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムに発注要求メッセージを送信します。  
  
7.  業者の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムは、この発注要求メッセージを受信します。 (応答が不要な) シングル アクションの要求の場合、業者の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムは、このメッセージの受信を確認するシグナル メッセージを返します。 ただしダブル アクションのメッセージでは、業者の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムは受信確認のシグナル メッセージの後で応答メッセージも返します。  
  
8.  業者の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムは発注要求メッセージから RNIF ヘッダーを削除し、メッセージの Service Content を処理して、業者の ERP システムに要求をルーティングします。  
  
9. 業者の従業員は ERP システムを使って注文を処理します。 メッセージを部品供給業者に送信しなければならない場合は、同じ BizTalk と [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムを使用して送信します。 IT 部門は、製造元に自動的に応答する、システムをカスタマイズできます。  
  
10. 従業員は業者の ERP システムを使用して発注応答メッセージを生成し、業者の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムにルーティングします。  
  
11. 業者の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムは PIP 3A4 発注応答メッセージを作成し、応答メッセージの Service Content を RNIF ヘッダーでラップしてから、メーカーの [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムに送信します。  
  
12. メーカーの [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムが発注応答を受信し、受信確認メッセージを業者の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] に送信します。 業者の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] システムは、業者の ERP システムにこの確認メッセージをルーティングします。  
  
13. メーカーの [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は応答メッセージから RNIF ヘッダーを削除し、Service Content を処理して、メーカーの ERP アプリケーションにルーティングします。  
  
14. メーカーの従業員がすべての発注確認メッセージを分析し、発注元の顧客へ送信する発注確認の応答メッセージを作成します。 この応答メッセージを電子メールで送信します。  
  
## <a name="advantages-of-the-btarn-solution"></a>BTARN ソリューションの利点  
 発注要求および応答プロセスの大部分は、BizTalk Server と [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] によって自動化されます。 メーカーと IC 供給業者に関するプロセスだけではなく、サプライ チェーン管理の一環として RosettaNet に準拠するソリューションを採用した他のすべての取引先とのプロセスも自動化されます。  
  
 統合システムは、手動の操作と使用する用紙の量を最小限に抑えます。 ほとんどのプロセスで、統合されたサーバー コンピューター間での処理が自動化されています。 プロセスはメーカーと IC 供給業者の両方で視覚的に管理できます。 どちらも受信確認を自動受信することで、否認不可性を維持することができます。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を使用した自動システムにより、メーカーと業者は以下のことを実現できます。  
  
-   注文処理のサイクル時間の短縮  
  
-   プロセスにおける不確定要素の削減と、プロセスの信頼性の向上  
  
-   処理時間および見積もり応答時間の短縮  
  
-   手動での情報の再入力、不足情報の取得、エラー修正作業に要する時間の削減  
  
-   メッセージのプロセスおよび追跡を視覚的に監視  
  
## <a name="see-also"></a>参照  
 [BizTalk Server がビジネス ニーズを解決する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [取引先との統合の必要性](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md)   
 [サプライ チェーンの課題](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md)   
 [サプライ チェーン ソリューション](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md)   
 [サンプルのハブベース シナリオ](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md)