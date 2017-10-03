---
title: "BAM 管理ユーティリティを使用して BAM 構成を更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 714a834e-1879-4019-9b54-e511705bd67a
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee5958120e364cc0c2661ead6100bd2ba5502226
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="c3e49-102">BAM 管理ユーティリティを使用して BAM 構成を更新する方法</span><span class="sxs-lookup"><span data-stu-id="c3e49-102">How to Update the BAM Configuration Using the BAM Management Utility</span></span>
<span data-ttu-id="c3e49-103">管理者は、BAM 管理ユーティリティを使用して、既存の BAM を更新できます。</span><span class="sxs-lookup"><span data-stu-id="c3e49-103">Administrators can use the BAM Management utility to update an existing BAM installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c3e49-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="c3e49-104">Prerequisites</span></span>  
 <span data-ttu-id="c3e49-105">更新された BAM データベースに対する管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3e49-105">You must have Administrator permissions on the BAM database being updated.</span></span>  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="c3e49-106">BAM 管理ユーティリティを使用して BAM 構成を更新するには</span><span class="sxs-lookup"><span data-stu-id="c3e49-106">To update the BAM configuration using the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="c3e49-107">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="c3e49-107">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="c3e49-108">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。</span><span class="sxs-lookup"><span data-stu-id="c3e49-108">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="c3e49-109">コマンド ライン プロンプトで、次を入力: **bm 更新 config ファイル名:\<構成ファイル >**ここで、 \<*構成ファイル*> は、BAM の名前に置換構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c3e49-109">Type the following at the command line prompt: **bm update-config -FileName:\<config file>**, where \<*configuration file*> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="c3e49-110">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c3e49-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e49-111">参照</span><span class="sxs-lookup"><span data-stu-id="c3e49-111">See Also</span></span>  
 [<span data-ttu-id="c3e49-112">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="c3e49-112">BAM Management Utility</span></span>](../core/bam-management-utility.md)