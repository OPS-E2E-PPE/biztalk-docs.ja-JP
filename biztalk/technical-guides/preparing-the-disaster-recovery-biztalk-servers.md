---
title: ディザスター リカバリー BizTalk Server の準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14c2c25d-30c5-4e90-a744-f084befa2c1d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61e283233017723a5dbb014eae41073820a7f43d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279027"
---
# <a name="preparing-the-disaster-recovery-biztalk-servers"></a><span data-ttu-id="3c436-102">ディザスター リカバリー BizTalk Server の準備</span><span class="sxs-lookup"><span data-stu-id="3c436-102">Preparing the Disaster Recovery BizTalk Servers</span></span>
<span data-ttu-id="3c436-103">インストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、推奨事項に従い、ディザスター リカバリー サイトでの実行時サーバー [BizTalk Server 2010 インストールおよびアップグレード ガイド](http://go.microsoft.com/fwlink/?LinkID=194815)(<http://go.microsoft.com/fwlink/?LinkID=194815>)。</span><span class="sxs-lookup"><span data-stu-id="3c436-103">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers at the disaster recovery site following the recommendations in [BizTalk Server 2010 Installation and Upgrade Guides](http://go.microsoft.com/fwlink/?LinkID=194815) (<http://go.microsoft.com/fwlink/?LinkID=194815>).</span></span> <span data-ttu-id="3c436-104">これらの構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム サーバーを BizTalk 構成ウィザードを使用して、運用環境の BizTalk グループに参加させます。</span><span class="sxs-lookup"><span data-stu-id="3c436-104">Configure these [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers using the BizTalk Configuration Wizard to join them to the production BizTalk group.</span></span> <span data-ttu-id="3c436-105">構成するときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (ディザスター リカバリーのエンタープライズ シングル サインオン マスター シークレット サーバーを含む) のディザスター リカバリー サイトでの実行時のサーバーを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c436-105">When configuring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers at the disaster recovery site (including the disaster recovery Enterprise Single Sign-On Master Secret server) make sure to:</span></span>  
  
- <span data-ttu-id="3c436-106">選択**いいえ**「これはマスター シークレット サーバーとは」質問する</span><span class="sxs-lookup"><span data-stu-id="3c436-106">Select **No** to the question “Is this the master secret server?”</span></span>  
  
- <span data-ttu-id="3c436-107">選択**結合**の質問に"Do you want を作成または BizTalk Server グループに参加しますか?"</span><span class="sxs-lookup"><span data-stu-id="3c436-107">Select **Join** to the question “Do you want to create or join a BizTalk Server group?”</span></span>  
  
  <span data-ttu-id="3c436-108">構成した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時の障害回復サーバーでは、実稼働サイトのホスト インスタンスに対応していますが、これらのホスト インスタンスを起動しないが、ディザスター リカバリー サイトでの BizTalk ホスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c436-108">After configuring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time disaster recovery servers, create BizTalk host instances on the disaster recovery site that correspond to the production site host instances, but do not start these host instances.</span></span> <span data-ttu-id="3c436-109">たとえば、実稼働サイトがある 3 つのホスト**送信**、**受信**、および**オーケストレーション**server1、server2 というと server3 インスタンス、対応する 3 つの作成DRserver1、DRserver2、DRserver3 上のインスタンスをホストします。</span><span class="sxs-lookup"><span data-stu-id="3c436-109">For example, if the production site has three Hosts **Send**, **Receive**, and **Orchestration** with instances on server1, server2, and server3, create three corresponding host instances on DRserver1, DRserver2, DRserver3.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c436-110">すべて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-Windows サービス、BizTalk ホスト インスタンスと、ディザスター リカバリー サイトでのルール エンジンのサービスに設定する"disabled"サービス マネージャーで、ディザスター リカバリー サイトが、処理を実行するを防ぐためになどに関連します。</span><span class="sxs-lookup"><span data-stu-id="3c436-110">All [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related Windows services such as the BizTalk Host Instance and Rules Engine Service at the disaster recovery site should be set to “disabled” in the Services Manager to prevent the disaster recovery site from performing any processing.</span></span>  
  
 <span data-ttu-id="3c436-111">インストールして構成の数が異なる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境で実行しているよりも、ディザスター リカバリー サイトでの実行時のサーバー。</span><span class="sxs-lookup"><span data-stu-id="3c436-111">You can install and configure a different number of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers in the disaster recovery site than are running in production.</span></span> <span data-ttu-id="3c436-112">ディザスター リカバリーのイベントが発生した場合に、ディザスター リカバリー サイト内のサーバーをオーバー ロードを防ぐために、ただし、このアプローチを取る場合は、注意を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c436-112">Use caution when taking this approach however, so as to avoid overloading the servers in the disaster recovery site if a disaster recovery event occurs.</span></span> <span data-ttu-id="3c436-113">参加するスクリプトを実行できるデータベースのセットによって表される BizTalk グループを完全に復元され、BizTalk グループのすべての必要なシステム変更を実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時のサーバーを BizTalk グループにします。</span><span class="sxs-lookup"><span data-stu-id="3c436-113">Once the BizTalk group as represented by the set of databases is fully restored, and all required system changes are performed for the BizTalk group, scripts can be run to join the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers to the BizTalk group.</span></span>