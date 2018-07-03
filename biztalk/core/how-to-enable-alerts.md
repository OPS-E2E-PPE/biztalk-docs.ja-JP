---
title: アラートを有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enable-Alerts command [BAM]
- managing [BAM definitions], enabling alerts
- alerts, enabling
ms.assetid: 18f494b7-54fb-4aaf-89d1-7e3fe91f35c6
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9fee863613feea040e05856d8246f94b4a3f835
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969155"
---
# <a name="how-to-enable-alerts"></a><span data-ttu-id="d3dfc-102">警告を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="d3dfc-102">How to Enable Alerts</span></span>
<span data-ttu-id="d3dfc-103">管理者を使用して、**有効にするアラート**コマンドを指定されたビューにアラートをすべて有効にします。</span><span class="sxs-lookup"><span data-stu-id="d3dfc-103">Administrators use the **enable-alerts** command to enable all of the alerts on the specified view.</span></span>  
  
### <a name="to-enable-an-alert"></a><span data-ttu-id="d3dfc-104">警告を有効にするには</span><span class="sxs-lookup"><span data-stu-id="d3dfc-104">To enable an alert</span></span>  
  
1. <span data-ttu-id="d3dfc-105">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="d3dfc-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="d3dfc-106">コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、</span><span class="sxs-lookup"><span data-stu-id="d3dfc-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="d3dfc-107">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d3dfc-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="d3dfc-108">型**bm 有効にするアラートの表示:\<ビュー名\>** します。</span><span class="sxs-lookup"><span data-stu-id="d3dfc-108">Type **bm enable-alerts -View:\<view name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d3dfc-109">BAM 構成を XML としてエクスポートした場合は、警告に関連した XML を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="d3dfc-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="d3dfc-110">警告に関連した XML を変更し、その変更を配置した場合、bm.exe によって変更が検出され、BAM 警告が有効になります。</span><span class="sxs-lookup"><span data-stu-id="d3dfc-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4. <span data-ttu-id="d3dfc-111">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d3dfc-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3dfc-112">参照</span><span class="sxs-lookup"><span data-stu-id="d3dfc-112">See Also</span></span>  
 <span data-ttu-id="d3dfc-113">[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="d3dfc-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="d3dfc-114">[BAM 管理ユーティリティ](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="d3dfc-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="d3dfc-115">ここにリンクの説明を入力する</span><span class="sxs-lookup"><span data-stu-id="d3dfc-115">enter link description here</span></span>](../core/how-to-disable-alerts.md)