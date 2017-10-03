---
title: "チェックリスト: フォールト トレランスや負荷分散と高可用性を実現する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c93cfc3-05b2-43ad-b0a9-b7f0d2596113
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72976dba4ed30ad6747d2d6175702110fe9730a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-providing-high-availability-with-fault-tolerance-or-load-balancing"></a>チェックリスト: フォールト トレランスと負荷分散と高可用性を実現します。
このトピックにフォールト トレランスの構成や、稼働環境のコンポーネントの負荷分散に完了する必要がありますのある手順について説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境を高可用性を提供します。 これらのコンポーネントのフォールト トレランスの構成により、システムを特定のコンポーネントが失敗した場合、操作を続行できます。  
  
|手順|リファレンス|  
|-----------|---------------|  
|複数の BizTalk ホスト インスタンスを作成し、ホストのクラスタ リングを必要とするこれらのアダプターのサポートを実装します。|[BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|高可用性を追跡ホストを構成します。|[BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|構成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上、クラスター化されたデータベース[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Windows server クラスター上のインスタンス。|[データベースの高可用性](../technical-guides/high-availability-for-databases.md)|  
|高可用性を追跡ホストを構成します。 追跡を有効にここで N は、BizTalk グループ内のメッセージ ボックス データベースの数には、少なくとも N + 1 個のホスト インスタンスがあることを確認します。|ホストの追跡を有効にするオプションを選択**ホストの追跡を許可する**上、**ホストのプロパティ** ダイアログ ボックスから使用可能な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 ホストのプロパティの設定の詳細については、トピックを参照してください。[ホストのプロパティを変更する方法](http://go.microsoft.com/fwlink/?LinkId=154359)(http://go.microsoft.com/fwlink/?LinkId=154359)。|  
|フェールオーバー機能するために定期的にデータベースのフェールオーバーを練習します。|この機能は、これが定期的に行われることを確認に直接割り当てる必要があります。|  
|複数を有効にするための十分な処理能力とパッシブ クラスター ノード上のメモリがあることを確認[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスにフェールオーバーのシナリオで同時に実行します。|2 つの SQL インスタンスで、個々 のクラスター ノード上のリソースの 50% が定期的に消費する以上場合、両方のインスタンスが 1 つのノードにフェールオーバーするときに各インスタンスは発生パフォーマンスが低下します。 そのため、1 つのクラスター ノードが、失敗したノードがオンラインに戻るまで、負荷を処理できることを確認するテストを実行する必要があります。 1 つのノードは、両方の SQL インスタンスの負荷を処理できない場合、アクティブ/アクティブ/パッシブ クラスター トポロジを実装する追加のクラスター ノードを追加することを検討します。|  
|家に記憶域エリア ネットワーク (SAN) を実装する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 **注:** RAID を使用して SAN ディスクの構成可能であれば、最高のパフォーマンスと高可用性トポロジを 1 + 0 (ストライプはミラー セット)。|[「BizTalk Server データベースの最適化のホワイト ペーパー」](http://go.microsoft.com/fwlink/?linkid=104427) (http://go.microsoft.com/fwlink/?linkid=104427)「パフォーマンス チューニング」下の「ディスク インフラストラクチャ」セクションを参照してください。|  
|エンタープライズ シングル サインオン (SSO) マスター シークレット サーバーをクラスター化するのにには、Windows クラスタ リングを使用します。|[マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)**注:**を実行しているコンピューターで SSO サービスをクラスター化しない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SSO と同じクラスター グループ内の BizTalk ホストをクラスター化する場合を除き、します。 SSO サービスをクラスタ リングの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]同じクラスター グループ内のホストを参照してください[クラスター SSO を同じクラスター グループ内の BizTalk ホスト](http://go.microsoft.com/fwlink/?LinkId=154367)(http://go.microsoft.com/fwlink/?LinkId=154367)。|  
|エンタープライズ シングル サインオン (SSO) マスター シークレットをバックアップします。|参照してください[マスター シークレットをバックアップする方法](http://go.microsoft.com/fwlink/?LinkID=151395)(http://go.microsoft.com/fwlink/?LinkID=151395)。|  
|インターネット インフォメーション サービス (IIS) Web サーバーの分離ホスト インスタンスと可用性が高いネットワーク負荷分散 (NLB) またはその他の負荷分散デバイスを使用して BAM ポータル Web ページ用に構成します。|**Windows Server 2008 の**: を参照してください[ネットワーク負荷分散展開ガイド](http://go.microsoft.com/fwlink/?LinkId=153139)(http://go.microsoft.com/fwlink/?LinkId=153139)。|  
  
## <a name="see-also"></a>参照  
 [高可用性を提供します。](../technical-guides/providing-high-availability.md)