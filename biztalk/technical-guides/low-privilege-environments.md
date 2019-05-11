---
title: 低い特権の環境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: abdc45d0-b63a-4b6c-80c4-1f8e87644cd9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 121655ecb70c084637f2fd481dc6bd2fce7a57cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396291"
---
# <a name="low-privilege-environments"></a><span data-ttu-id="97107-102">低い特権の環境</span><span class="sxs-lookup"><span data-stu-id="97107-102">Low-Privilege Environments</span></span>
<span data-ttu-id="97107-103">複数のワークフローに含まれている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックには、特定のアクションを実行する管理者特権での権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="97107-103">Several workflows that are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack require elevated permissions to perform certain actions.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="97107-104">管理パックでは、低い特権の環境での基本的な監視機能を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="97107-104">Management Pack enables you to perform basic monitoring functionalities in a low privilege environment.</span></span> <span data-ttu-id="97107-105">2 つの管理ロール: BizTalk Server 管理者、および BizTalk Server Operator します。</span><span class="sxs-lookup"><span data-stu-id="97107-105">There are two Administrative Roles: the BizTalk Server Administrator, and the BizTalk Server Operator.</span></span> <span data-ttu-id="97107-106">BizTalk Server の管理者は、構成データおよび追跡データへのアクセスを高い特権を持つロールです。</span><span class="sxs-lookup"><span data-stu-id="97107-106">The BizTalk Server Administrator is a high privilege role with access to configuration and tracking data.</span></span> <span data-ttu-id="97107-107">BizTalk Server の管理者は、このような参加と成果物を開始、すべてのキー管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="97107-107">The BizTalk Server Administrator can perform all key administrative tasks such enlisting and starting artifacts.</span></span> <span data-ttu-id="97107-108">BizTalk Server Operator は、監視とトラブルシューティング操作にのみアクセス権を持つ特権の低いロールです。</span><span class="sxs-lookup"><span data-stu-id="97107-108">The BizTalk Server Operator is a low privilege role with access only to monitoring and troubleshooting actions.</span></span> <span data-ttu-id="97107-109">詳細については、次を参照してください。[最小セキュリティ ユーザー権限](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="97107-109">For more information, see [Minimum Security User Rights](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx).</span></span>  
  
 <span data-ttu-id="97107-110">使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パック。</span><span class="sxs-lookup"><span data-stu-id="97107-110">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack:</span></span>  
  
-   <span data-ttu-id="97107-111">BizTalk Server Operator グループのメンバは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="97107-111">Members of the BizTalk Server Operators group can do the following:</span></span>  
  
    -   <span data-ttu-id="97107-112">BizTalk Server の監視のエラー、中断された messages\instances、構成の表示をクエリします。</span><span class="sxs-lookup"><span data-stu-id="97107-112">Monitor BizTalk Server for errors, query for suspended messages\instances, view configuration.</span></span>  
  
    -   <span data-ttu-id="97107-113">BizTalk Server のインストールと成果物を監視します。</span><span class="sxs-lookup"><span data-stu-id="97107-113">Monitor BizTalk Server installations and artifacts.</span></span>  
  
    -   <span data-ttu-id="97107-114">サービスの状態とメッセージ フローの表示。</span><span class="sxs-lookup"><span data-stu-id="97107-114">View service state and message flow.</span></span>  
  
    -   <span data-ttu-id="97107-115">開始または停止アプリケーションやオーケストレーションなどの成果物、送信ポートまたは送信ポート グループに参加している状態にあります。</span><span class="sxs-lookup"><span data-stu-id="97107-115">Start or stop applications and artifacts such as orchestrations, send ports or send port groups that are in an enlisted state.</span></span>  
  
    -   <span data-ttu-id="97107-116">受信場所の有効化または無効化。</span><span class="sxs-lookup"><span data-stu-id="97107-116">Enable or disable receive locations.</span></span> <span data-ttu-id="97107-117">変更は、次回のキャッシュ更新の後で有効になります。キャッシュの更新間隔は既定では 60 秒で、</span><span class="sxs-lookup"><span data-stu-id="97107-117">The changes do not take effect until the next cache refresh interval of 60 seconds, which is the default.</span></span> <span data-ttu-id="97107-118">BizTalk Server のグループ レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="97107-118">The cache refresh interval is set at the BizTalk Server group level.</span></span>  
  
-   <span data-ttu-id="97107-119">BizTalk Server Operators グループのメンバは、次の操作を実行できません。</span><span class="sxs-lookup"><span data-stu-id="97107-119">Members of the BizTalk Server Operators group cannot do the following:</span></span>  
  
    -   <span data-ttu-id="97107-120">BizTalk Server の構成の変更。</span><span class="sxs-lookup"><span data-stu-id="97107-120">Modify the configuration for BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="97107-121">個人情報 (PII) に分類されるメッセージ コンテキストのプロパティまたはメッセージ本文の表示。</span><span class="sxs-lookup"><span data-stu-id="97107-121">View message context properties classified as Personally Identifiable Information (PII) or message bodies.</span></span>  
  
    -   <span data-ttu-id="97107-122">実行中のシステムに対するサブスクリプションを削除や追加など、メッセージ ルーティングのコースを変更する操作。これには BizTalk Server ランタイムへのメッセージの公開も含まれます。</span><span class="sxs-lookup"><span data-stu-id="97107-122">Modify the course of message routing, such as removing or adding new subscriptions to the running system, including the ability to publish messages into the BizTalk Server runtime.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97107-123">BTSNTSvc.exe サービスを再起動するなどの管理パックによって提供されるすべての監視タスクを実行するには、BizTalk サーバーでローカルの Administrators グループのメンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="97107-123">To perform all monitoring tasks provided by the Management Pack such as restarting BTSNTSvc.exe service, you must be a member of the local Administrators group on the BizTalk Servers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="97107-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="97107-124">In this section</span></span>  
  
-   [<span data-ttu-id="97107-125">監視</span><span class="sxs-lookup"><span data-stu-id="97107-125">Monitoring</span></span>](../technical-guides/monitoring.md)  
  
-   [<span data-ttu-id="97107-126">検出</span><span class="sxs-lookup"><span data-stu-id="97107-126">Discoveries</span></span>](../technical-guides/discoveries.md)