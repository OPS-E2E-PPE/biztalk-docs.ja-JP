---
title: アプリケーションを復元し、処理を有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83144965-a51a-481a-afd6-7f573b69badb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4c73d3ac6d96b1cfae4a8e8092669b6b0edcad0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400297"
---
# <a name="how-to-restore-applications-and-enable-processing"></a><span data-ttu-id="777d2-102">アプリケーションを復元し、処理を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="777d2-102">How to Restore Applications and Enable Processing</span></span>
<span data-ttu-id="777d2-103">BizTalk グループで、アプリケーションを構成し、次のトピックで説明する手順の後にアプリケーションの処理を有効にする[ランタイム コンピューターの更新方法](../technical-guides/how-to-update-the-runtime-computers.md)します。</span><span class="sxs-lookup"><span data-stu-id="777d2-103">Configure the applications in the BizTalk group and enable application processing after following the steps described in the topic [How to Update the Runtime Computers](../technical-guides/how-to-update-the-runtime-computers.md).</span></span>  
  
### <a name="to-enable-application-configuration-and-restore-application-processing"></a><span data-ttu-id="777d2-104">アプリケーションの構成を有効にして、アプリケーションの処理を復元するには</span><span class="sxs-lookup"><span data-stu-id="777d2-104">To enable application configuration and restore application processing</span></span>  
  
1. <span data-ttu-id="777d2-105">実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ内の各 BizTalk サーバー上のアプリケーションのインストールの MSI ファイルです。</span><span class="sxs-lookup"><span data-stu-id="777d2-105">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Installation MSI file on each BizTalk server in the group.</span></span>  
  
2. <span data-ttu-id="777d2-106">実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ディザスター リカバリー サイトのアプリケーションを構成するには、グループの 1 つのサーバー上のアプリケーション構成の MSI ファイルです。</span><span class="sxs-lookup"><span data-stu-id="777d2-106">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Configuration MSI file on one server in the group to configure the application for the disaster recovery site.</span></span> <span data-ttu-id="777d2-107">名前は、受信場所と送信ポートは変わりません。</span><span class="sxs-lookup"><span data-stu-id="777d2-107">The names for receive locations and send ports remain the same.</span></span> <span data-ttu-id="777d2-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をこれらの成果物が、ディザスター リカバリー環境で適切な場所を指すように、アプリケーション構成の MSI ファイルがバインドを更新します。</span><span class="sxs-lookup"><span data-stu-id="777d2-108">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Configuration MSI file updates bindings so that these artifacts point to the correct locations in the disaster recovery environment.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="777d2-109">場合は受信場所と送信ポートには影響しません、実稼働サイトの損失、いない必要がありますディザスター リカバリ固有の場所を使用してアプリケーションを再構成します。</span><span class="sxs-lookup"><span data-stu-id="777d2-109">If receive locations and send ports are not affected by the loss of the production site, it may not be necessary to reconfigure the application with disaster recovery-specific locations.</span></span>  
  
3. <span data-ttu-id="777d2-110">すべてのアプリケーションを有効にすると復元にアプリケーションの処理では、受信場所、ポート、およびホスト インスタンスを送信します。</span><span class="sxs-lookup"><span data-stu-id="777d2-110">Restore application processing by enabling all application receive locations, send ports, and host instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="777d2-111">参照</span><span class="sxs-lookup"><span data-stu-id="777d2-111">See Also</span></span>  
 [<span data-ttu-id="777d2-112">ランタイム コンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="777d2-112">Recovering the Runtime Computers</span></span>](../technical-guides/recovering-the-runtime-computers.md)