---
title: サンプル サプライ チェーンのシナリオ |Microsoft Docs
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
ms.openlocfilehash: c9b338a2dea65c9d1ccd86cf46daa736d2c4044a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282120"
---
# <a name="sample-supply-chain-scenario"></a>サンプル サプライ チェーン シナリオ
ハイテク サプライ チェーンの最も基本的なプロセスの 1 つは、発注要求および応答メッセージの交換です。 購入者が発注書を発行し、かどうかを承諾または拒絶、順序、注文が保留中かどうかや、行レベルで、仕入先を確認します。  
  
 このトピックでは、発注書メッセージを交換する 2 つの取引のサンプル シナリオについて説明し、統合と自動化のプロセスを改善する方法を示しています。  
  
## <a name="the-players"></a>プレイヤー  
 このサンプル シナリオでは、購入者は、大規模なハイテク装置メーカーです。 現在、自動化されたデータ交換 EDI ベースのシステムを使用します。 依存している EDI を使用して仕入先と電話、fax、スプレッドシート、および Web アプリケーションを電子メールで送信します。 EDI を使用する業者を使用しても、取引先パートナーとの通信をバックエンド ERP システムと統合する機能が制限があります。 EDI を介して注文と情報を受信した後する必要があります手動で再入力これらの注文を ERP システムにします。 要求を自動化することで、既存のサプライ チェーン プロセスを改善するインベントリ、購入、および取引先パートナーとレポートします。 これらには、そのサプライヤーや、既存の基幹業務 (LOB) アプリケーションと直接連携することも、インターネット経由の顧客とつながるのシステムが必要です。  
  
 販売者は、高性能 ic) の規模のサプライヤーです。 現在電話を使用して、取引先パートナーとの通信、fax、電子メールで Microsoft に接続されている[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシート、FTP、および Web アプリケーション。 EDI は使わないでください。 各取引先パートナーとの対話は、顧客や、独自のテクノロジのニーズによって異なります。 トランザクションのコストを削減し、顧客満足度を向上させ、競争力を高めより効率的なビジネス プロセスを作成します。  
  
## <a name="the-present-business-process"></a>現在のビジネス プロセス  
 統合ソリューションをせずメーカーと業者の発注プロセスは次のように動作します。  
  
1. ハイテク装置メーカーの顧客は、Web サイトを製造元に注文を送信します。  
  
2. 元の順序に対応してでは、メーカーの従業員は、IC 供給業者側の LOB ERP アプリケーションで発注要求を作成します。  
  
3. 発注要求は、記録、処理、確認、および発注要求を承認する必要がある製造会社のさまざまな関係者を走査します。 この処理とルーティングは、ERP システムのユーザーの自動化されたプロセスと電子メールの添付など、手動のプロセスを組み合わせた[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシートです。  
  
4. 従業員は、電子メールで発注要求を作成し、業者に送信します。 他のサプライヤーに電子メール、fax、または EDI 経由で通信する他の従業員数は、このプロセスを繰り返します。 さまざまな部門では、別のプロセスを使用します。 EDI を使用する業者、メーカーの従業員する必要がありますもメッセージを手動で作成、ERP システムから。  
  
5. 供給業者の従業員は、メッセージを受信して、し、手動でキーが、ERP システムにデータの形式を変更します。 電子メールを使用して、従業員には、要求の他の従業員に通知します。  
  
6. 他の従業員は、要求を分析します。 必要な場合は、部品の必要性を独自の部品サプライヤーに通知されます。 業者に応じて、それらを使用して、電話、fax、電子メール、または FTP で通知します。  
  
7. 部署および業者と話し合うには、後に各従業員を受け入れるまたは購買注文製品の行項目、拒否したことを確認しますまたは、発注書を拒否し、保留中であることを示します。 ERP システムでこれらのタスクを実行します。  
  
8. いずれかの確認または各品目の要求を拒否しています、業者の従業員が電子メールでは、発注応答を作成するかが保留中であることを示すメッセージを作成するには、注文書。 業者の従業員は、製造元に、応答メッセージを送信します。 行項目が保留中の場合は、後で保留中の項目が受け入れられるか拒否されるかどうかを示す別のメッセージを作成します。  
  
9. メーカーの従業員は発注応答を受信します。 再バックエンド ERP システムに注文を入力します。  
  
10. 別の従業員は発注書の確認を分析し、注文の確認、元の顧客への応答を作成します。 この応答を電子メールを送信します。  
  
## <a name="the-rosettanet-solution"></a>RosettaNet ソリューション  
 Microsoft BizTalk Server と[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]を自動化し、発注要求および応答プロセスを標準化します。 統合システムを使用して、処理、および電話と fax のマシンを使用して、用紙の量の手動操作の量を最小限に抑えられます。 ほとんどのプロセスは、統合されたサーバーのコンピューター間で自動トランザクションです。 従業員は、操作を手動で実行する必要があります、ときに、通常はバックエンド ERP システムで。 次の図は、統合システムを示しています。  
  
 ![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-integrated-supply-chain-scenario.gif "RN3_Integrated_Supply_Chain_Scenario")  
  
 このシナリオでは、統合システムは、次のプロセスを変更します。  
  
- RosettaNet Implementation Framework (RNIF) の接続には、メーカーと IC 供給業者側の間で日常的な手動操作が置き換えられます。 システムに自動的に送信しメッセージを受信、バックエンド システムにデータをルーティングしかを確認し、、メッセージに応答します。 製造元とを使用して仕入先の両方[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]RNIF 接続を実装します。  
  
- RNIF 接続には、製造元、IC 供給業者、およびその他の取引先パートナーとの間 EDI 接続が置き換えられます。 これにより、取引先のバックエンド システムに自動的に統合システムのルート データ。 取引先のいくつかのパートナー使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]RNIF 接続を実装するためにさまざまな RosettaNet 準拠のソリューションを使用して、他のユーザー。  
  
- 小規模なパートナーについて、RosettaNet 準拠のソリューションがない、メーカーと IC 供給業者は Web ブラウザーを使用して、パートナーがアクセスできる Web サービスを作成します。 Web サービスとの通信に、標準の RNIF 接続を使用して、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システム、製造元または IC 供給業者側のいずれかにします。  
  
- 製造元によって交換されるメッセージと業者の標準的な RosettaNet Partner Interface Process (Pip) に準拠するスキーマ。 これらのスキーマは、EDI と FTP で使用される形式を置き換えます。 すべての取引を使用して、同じスキーマです。メッセージ間のデータをマップするはありません。  
  
- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] データ エラーの危険性の低下、スキーマに対してすべてのメッセージを自動的に検証します。  
  
- 管理者は、上で操作できます[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]サーバーの管理ソフトウェア ツールを使用します。 クライアント コンピューターでビジネスの意思決定者は、Microsoft Office ベースのアプリケーションまたはツールでホストされているビジネス監視ツールを使用できます。 効果的にオペレーティング システムを維持する効率的なプロセスし、方法に可視性を提供します。 これらの両方、システム-方法と、ビジネス-が実行されています。  
  
### <a name="message-flow"></a>メッセージ フロー  
 ここで、ビジネス プロセスには、次の手順が含まれます。  
  
1. ハイテク装置メーカーの顧客は、Web サイトを製造元に注文を送信します。  
  
2. 元の順序に対応してでは、メーカーの従業員は会社の注文や在庫管理システムで発注要求を生成します。 この LOB アプリケーションは、Web ベースのユーザー インターフェイスと ERP システムです。  
  
3. システムによる発注書要求を送信します、ERP システムにネイティブ形式のままでに[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]します。  
  
4. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RosettaNet 組織で定義されている 3A4 PIP に準拠した発注要求メッセージを自動的に生成されます。 この発注要求は XML 形式です。 PIP では、メッセージの内容を定義します。  
  
   > [!NOTE]
   >  3A4 PIP は、すべての発注書の要求と応答は、フォームで同じであることを確認します。 この PIP は、完全に相互接続されたメッセージング システムを形成する Pip の RosettaNet 定義のコレクションの一部です。 たとえば、3A4 メッセージを送信する前に価格を検索、購入者や可用性 (PIP 3 a 2) (PIP 3A1)、見積もりの要求 (PIP 3A3) ショッピング カート転送します。 発注書要求を送信すると、購入者可能性があります (PIP 3A8) 購入順序を変更、発注書 (PIP 3A9) をキャンセル、購買注文の状態 (PIP 3A5) に対してクエリを実行または配布発注状態の (配信 PIP 3A6)。 RosettaNet 組織には、これらすべてのメッセージが標準化されています。  
  
5. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNIF ヘッダーで (名前付き、service content)、要求メッセージをラップ[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]別に、インターネット経由でメッセージの送信[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]業者サイトのコンピューター。 RNIF は、パートナーがインターネット経由でメッセージを交換する方法を定義します。  
  
6. 製造元の[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システム IC 供給業者の発注書の要求が送信[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システム。  
  
7. 供給業者の[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]N システムが発注書要求を受信します。 (対応する応答がない 1 つ)、シングル アクション要求した場合、業者の[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システムは、メッセージの受信を確認するシグナル メッセージを返します。 ただし、これは、ダブル アクション メッセージを業者のため、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システムは応答メッセージも後に受信確認シグナル メッセージを返します。  
  
8. 供給業者の[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システム、発注要求メッセージから RNIF ヘッダーを削除、メッセージの service content を処理および業者の ERP システムに要求をルーティングします。  
  
9. 業者の従業員は、注文を処理する ERP システムで動作します。 独自の部品サプライヤーにメッセージを送信する場合は、それによって、同じ biztalk と[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システム。 IT 部門は、製造元に自動的に応答するシステムをカスタマイズできます。  
  
10. 従業員は業者の ERP システムを使用して、発注応答メッセージを生成して、応答メッセージをルーティングし、業者の[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システム。  
  
11. 供給業者の[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システムは、PIP 3A4 発注応答メッセージが生成され、応答メッセージの service content を RNIF ヘッダーでラップし、メーカーの発注応答を送信[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システム。  
  
12. 製造元の[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システム発注応答を受信し、業者の受信確認メッセージを送信[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]します。 供給業者の[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]システムが業者の ERP システムに受信確認をルーティングします。  
  
13. 製造元の[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]応答メッセージから RNIF ヘッダーを削除、サービスのコンテンツを処理し、製造元の ERP アプリケーションに発注応答をルーティングします。  
  
14. メーカーの従業員は、すべての発注書確認メッセージを分析し、注文の確認、元の顧客への応答を作成します。 従業員は電子メールでは、この応答を送信します。  
  
## <a name="advantages-of-the-btarn-solution"></a>BTARN ソリューションの利点  
 BizTalk Server と[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]発注要求および応答プロセスの大部分を自動化します。 それによって、メーカーと IC 供給業者側でだけでなく、サプライ チェーン管理の一環として RosettaNet 準拠のソリューションを採用している他のすべての取引先に対してもします。  
  
 システムの統合には、手動介入の量と、用紙の量が最小限に抑えます。 ほとんどのプロセスには、統合されたサーバーのコンピューター間で自動化されたインタラクションが含まれます。 メーカーと IC 供給業者側の両方のそのプロセスの可視性と制御、高度ながあります。 受信確認を受信して、否認不可性を維持できますが自動的には。  
  
 自動化されたシステムを使用して、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]メーカーと業者は、以下を実行できるようにします。  
  
-   注文調達のサイクル時間を短縮します。  
  
-   プロセスにおける不確定要素を削減し、プロセスの信頼性を向上させる  
  
-   処理時間および見積もり応答時間を減らす  
  
-   不足情報の取得、またはエラーを修正する時間を手動で再情報を削減します。  
  
-   可視性を提供し、プロセスの監視と、メッセージの追跡を有効にします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server がビジネス ニーズを解決する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [取引先との統合の必要性](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md)   
 [サプライ チェーンの課題](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md)   
 [サプライ チェーン ソリューション](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md)   
 [サンプルのハブベース シナリオ](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md)