---
title: BAM 管理ユーティリティを使用して BAM 構成を更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 714a834e-1879-4019-9b54-e511705bd67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f497fa345dd643429dac7c48d43e04646fd81f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333698"
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="212cf-102">BAM 管理ユーティリティを使用して BAM 構成を更新する方法</span><span class="sxs-lookup"><span data-stu-id="212cf-102">How to Update the BAM Configuration Using the BAM Management Utility</span></span>
<span data-ttu-id="212cf-103">管理者は、BAM 管理ユーティリティを使用して、既存の BAM のインストールを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="212cf-103">Administrators can use the BAM Management utility to update an existing BAM installation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="212cf-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="212cf-104">Prerequisites</span></span>  
 <span data-ttu-id="212cf-105">管理者のアクセス許可は、更新された BAM データベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="212cf-105">You must have Administrator permissions on the BAM database being updated.</span></span>  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a><span data-ttu-id="212cf-106">BAM 管理ユーティリティを使用して BAM 構成を更新するには</span><span class="sxs-lookup"><span data-stu-id="212cf-106">To update the BAM configuration using the BAM Management utility</span></span>  
  
1. <span data-ttu-id="212cf-107">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="212cf-107">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="212cf-108">移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。</span><span class="sxs-lookup"><span data-stu-id="212cf-108">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="212cf-109">コマンド ライン プロンプトで、次の入力: **bm 更新プログラム構成ファイル名:\<config ファイル\>** ここで、 \<*構成ファイル*\>はBAM 構成ファイルの名前で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="212cf-109">Type the following at the command line prompt: **bm update-config -FileName:\<config file\>**, where \<*configuration file*\> is replaced by the name of your BAM configuration file.</span></span> <span data-ttu-id="212cf-110">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="212cf-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="212cf-111">参照</span><span class="sxs-lookup"><span data-stu-id="212cf-111">See Also</span></span>  
 [<span data-ttu-id="212cf-112">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="212cf-112">BAM Management Utility</span></span>](../core/bam-management-utility.md)