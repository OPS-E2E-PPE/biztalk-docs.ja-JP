---
title: "アプリケーションを復元し、処理を有効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83144965-a51a-481a-afd6-7f573b69badb
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65ae913d45f45b13458294863714823a41ff4e44
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-restore-applications-and-enable-processing"></a><span data-ttu-id="326c1-102">アプリケーションを復元し、処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="326c1-102">How to Restore Applications and Enable Processing</span></span>
<span data-ttu-id="326c1-103">BizTalk グループで、アプリケーションを構成し、次のトピックで説明した手順の後にアプリケーションの処理を有効にする[ランタイム コンピューターを更新する方法](../technical-guides/how-to-update-the-runtime-computers.md)です。</span><span class="sxs-lookup"><span data-stu-id="326c1-103">Configure the applications in the BizTalk group and enable application processing after following the steps described in the topic [How to Update the Runtime Computers](../technical-guides/how-to-update-the-runtime-computers.md).</span></span>  
  
### <a name="to-enable-application-configuration-and-restore-application-processing"></a><span data-ttu-id="326c1-104">アプリケーションの構成を有効にして、アプリケーションの処理を復元するには</span><span class="sxs-lookup"><span data-stu-id="326c1-104">To enable application configuration and restore application processing</span></span>  
  
1.  <span data-ttu-id="326c1-105">実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ内の各 BizTalk サーバー上のアプリケーションのインストールの MSI ファイル。</span><span class="sxs-lookup"><span data-stu-id="326c1-105">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Installation MSI file on each BizTalk server in the group.</span></span>  
  
2.  <span data-ttu-id="326c1-106">実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を構成して、障害復旧サイトのアプリケーション グループ内の 1 つのサーバー上のアプリケーション構成の MSI ファイル。</span><span class="sxs-lookup"><span data-stu-id="326c1-106">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Configuration MSI file on one server in the group to configure the application for the disaster recovery site.</span></span> <span data-ttu-id="326c1-107">名前は、受信場所と送信ポートは変わりません。</span><span class="sxs-lookup"><span data-stu-id="326c1-107">The names for receive locations and send ports remain the same.</span></span> <span data-ttu-id="326c1-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション構成の MSI ファイルがこれらの成果物が、障害回復環境で適切な場所を指すように、バインドを更新します。</span><span class="sxs-lookup"><span data-stu-id="326c1-108">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Configuration MSI file updates bindings so that these artifacts point to the correct locations in the disaster recovery environment.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="326c1-109">場合は受信場所と送信ポートには影響しません、実稼働サイトの損失、ある可能性がありますいないを災害復旧に固有の場所を使用してアプリケーションを再構成する必要です。</span><span class="sxs-lookup"><span data-stu-id="326c1-109">If receive locations and send ports are not affected by the loss of the production site, it may not be necessary to reconfigure the application with disaster recovery-specific locations.</span></span>  
  
3.  <span data-ttu-id="326c1-110">すべてのアプリケーションを有効にして復元アプリケーションの処理では、受信場所、ポート、およびホスト インスタンスを送信します。</span><span class="sxs-lookup"><span data-stu-id="326c1-110">Restore application processing by enabling all application receive locations, send ports, and host instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="326c1-111">参照</span><span class="sxs-lookup"><span data-stu-id="326c1-111">See Also</span></span>  
 [<span data-ttu-id="326c1-112">ランタイム コンピューターを回復します。</span><span class="sxs-lookup"><span data-stu-id="326c1-112">Recovering the Runtime Computers</span></span>](../technical-guides/recovering-the-runtime-computers.md)