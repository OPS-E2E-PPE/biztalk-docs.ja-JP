---
title: "災害復旧の BizTalk サーバーを準備する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14c2c25d-30c5-4e90-a744-f084befa2c1d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9379136f0845c7c4c987170747a28bd3c50206c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-the-disaster-recovery-biztalk-servers"></a><span data-ttu-id="e199d-102">災害復旧の BizTalk サーバーを準備します。</span><span class="sxs-lookup"><span data-stu-id="e199d-102">Preparing the Disaster Recovery BizTalk Servers</span></span>
<span data-ttu-id="e199d-103">インストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]推奨事項に従い、障害復旧サイトで実行時のサーバー [BizTalk Server 2010 インストールおよびアップグレード ガイド](http://go.microsoft.com/fwlink/?LinkID=194815)(http://go.microsoft.com/fwlink/?LinkID=194815)。</span><span class="sxs-lookup"><span data-stu-id="e199d-103">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers at the disaster recovery site following the recommendations in [BizTalk Server 2010 Installation and Upgrade Guides](http://go.microsoft.com/fwlink/?LinkID=194815) (http://go.microsoft.com/fwlink/?LinkID=194815).</span></span> <span data-ttu-id="e199d-104">これらの構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム サーバーの BizTalk 構成ウィザードを使用して、実稼働の BizTalk グループに参加させます。</span><span class="sxs-lookup"><span data-stu-id="e199d-104">Configure these [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers using the BizTalk Configuration Wizard to join them to the production BizTalk group.</span></span> <span data-ttu-id="e199d-105">構成するときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (災害復旧のエンタープライズ シングル サインオン マスター シークレット サーバーを含む)、災害復旧サイト サーバーの実行時間を確認します。</span><span class="sxs-lookup"><span data-stu-id="e199d-105">When configuring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers at the disaster recovery site (including the disaster recovery Enterprise Single Sign-On Master Secret server) make sure to:</span></span>  
  
-   <span data-ttu-id="e199d-106">選択**いいえ**「はこのマスター シークレット サーバーですか」という質問をする</span><span class="sxs-lookup"><span data-stu-id="e199d-106">Select **No** to the question “Is this the master secret server?”</span></span>  
  
-   <span data-ttu-id="e199d-107">選択**結合**の質問に「たい作成したり、BizTalk Server グループに参加しますか?」</span><span class="sxs-lookup"><span data-stu-id="e199d-107">Select **Join** to the question “Do you want to create or join a BizTalk Server group?”</span></span>  
  
 <span data-ttu-id="e199d-108">構成した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時の障害復旧サーバーでは、実稼働サイトのホスト インスタンスに対応しているが、これらのホスト インスタンスを開始できません災害復旧サイトで BizTalk ホスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e199d-108">After configuring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time disaster recovery servers, create BizTalk host instances on the disaster recovery site that correspond to the production site host instances, but do not start these host instances.</span></span> <span data-ttu-id="e199d-109">たとえば、実稼働サイトでは 3 つのホスト**送信**、**受信**、および**オーケストレーション**server1、server2、および server3 インスタンスは、対応する 3 つの作成DRserver1、DRserver2、DRserver3 上のインスタンスをホストします。</span><span class="sxs-lookup"><span data-stu-id="e199d-109">For example, if the production site has three Hosts **Send**, **Receive**, and **Orchestration** with instances on server1, server2, and server3, create three corresponding host instances on DRserver1, DRserver2, DRserver3.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e199d-110">すべて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-Windows サービス、BizTalk ホスト インスタンスと障害復旧サイトでルール エンジンのサービスする必要があります設定する「無効」にサービス マネージャーで、障害復旧サイトが、処理を実行するを防ぐためで関連します。</span><span class="sxs-lookup"><span data-stu-id="e199d-110">All [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related Windows services such as the BizTalk Host Instance and Rules Engine Service at the disaster recovery site should be set to “disabled” in the Services Manager to prevent the disaster recovery site from performing any processing.</span></span>  
  
 <span data-ttu-id="e199d-111">インストールして構成する数が異なる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境で実行しているよりも、障害復旧サイトでの実行時のサーバー。</span><span class="sxs-lookup"><span data-stu-id="e199d-111">You can install and configure a different number of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers in the disaster recovery site than are running in production.</span></span> <span data-ttu-id="e199d-112">障害復旧イベントが発生した場合、災害復旧サイト内のサーバーを過負荷を避けるため、ただし、このアプローチをとる場合は、注意を使用します。</span><span class="sxs-lookup"><span data-stu-id="e199d-112">Use caution when taking this approach however, so as to avoid overloading the servers in the disaster recovery site if a disaster recovery event occurs.</span></span> <span data-ttu-id="e199d-113">結合するスクリプトを実行できます、一連のデータベースで表される BizTalk グループが完全に復元され、BizTalk グループのすべての必要なシステム変更が実行される、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk グループにサーバーの実行時間。</span><span class="sxs-lookup"><span data-stu-id="e199d-113">Once the BizTalk group as represented by the set of databases is fully restored, and all required system changes are performed for the BizTalk group, scripts can be run to join the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers to the BizTalk group.</span></span>