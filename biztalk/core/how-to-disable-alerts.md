---
title: アラートを無効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- alerts, disabling
- managing [BAM definitions], disabling alerts
- Disable-Alerts command [BAM]
ms.assetid: c5938bc2-1043-4633-8cad-02caf442f2e8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac107300ff14f024da02d6959f695790fe7ff80
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002795"
---
# <a name="how-to-disable-alerts"></a><span data-ttu-id="41723-102">警告を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="41723-102">How to Disable Alerts</span></span>
<span data-ttu-id="41723-103">管理者を使用して、**無効にするアラート**コマンドは、指定されたビューにアラートをすべて無効にします。</span><span class="sxs-lookup"><span data-stu-id="41723-103">Administrators use the **disable-alerts** command to disable all of the alerts on the specified view.</span></span>  
  
### <a name="to-disable-an-alert"></a><span data-ttu-id="41723-104">警告を無効にするには</span><span class="sxs-lookup"><span data-stu-id="41723-104">To disable an alert</span></span>  
  
1. <span data-ttu-id="41723-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="41723-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="41723-106">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="41723-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="41723-107">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="41723-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="41723-108">型**bm の無効にするアラートの表示:\<ビュー名\>** します。</span><span class="sxs-lookup"><span data-stu-id="41723-108">Type **bm disable-alerts -View:\<view name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="41723-109">BAM 構成を XML としてエクスポートした場合は、警告に関連した XML を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="41723-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="41723-110">警告に関連した XML を変更し、その変更を配置した場合、bm.exe によって変更が検出され、BAM 警告が有効になります。</span><span class="sxs-lookup"><span data-stu-id="41723-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4. <span data-ttu-id="41723-111">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="41723-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41723-112">参照</span><span class="sxs-lookup"><span data-stu-id="41723-112">See Also</span></span>  
 <span data-ttu-id="41723-113">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="41723-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="41723-114">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="41723-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="41723-115">アラートを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="41723-115">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md)