---
title: 管理パックのモニタを表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7c4d2b3-9c01-40f5-b983-bf29a3a5cacc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d98cca640b7fa818ad49d3b9c95c3e3bdcbf5c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253480"
---
# <a name="how-to-display-monitors-for-a-management-pack"></a><span data-ttu-id="33574-102">管理パックのモニタを表示する方法</span><span class="sxs-lookup"><span data-stu-id="33574-102">How to Display Monitors for a Management Pack</span></span>
<span data-ttu-id="33574-103">管理パックのモニタおよび上書きコマンド シェルを使用して出力の一覧を表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="33574-103">To display a list of outputs for a management pack's monitors and overrides using the Command Shell, use the following procedure.</span></span>  
  
### <a name="to-display-monitors-for-a-management-pack"></a><span data-ttu-id="33574-104">管理パックのモニタを表示するには</span><span class="sxs-lookup"><span data-stu-id="33574-104">To display monitors for a management pack</span></span>  
  
1. <span data-ttu-id="33574-105">管理サーバーで次のようにクリックします。**プログラム**、 をクリックし、 **System Center。**</span><span class="sxs-lookup"><span data-stu-id="33574-105">In your management server, click **Programs**, and then click **System Center.**</span></span>  
  
2. <span data-ttu-id="33574-106">クリックして**コマンド シェル**します。</span><span class="sxs-lookup"><span data-stu-id="33574-106">Click **Command Shell**.</span></span>  
  
3. <span data-ttu-id="33574-107">コマンド シェルでは、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="33574-107">In the Command Shell, type the following command:</span></span>   
   `get-scommanagementpack –DisplayName “DisplayName” | get-scommonitor | export.csv filename`  
  
4. <span data-ttu-id="33574-108">.Csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="33574-108">A .csv file is created.</span></span> <span data-ttu-id="33574-109">.Csv ファイルは、Microsoft Office Excel で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="33574-109">The .csv file can be opened in Microsoft Office Excel.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="33574-110">Excel では、.csv ファイルをテキスト ファイルに指定する必要する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33574-110">In Excel, you may be required to specify that the .csv file is a text file.</span></span>  
  
   <span data-ttu-id="33574-111">たとえば、次のコマンドは、コア管理パックのいずれかに関連付けられているモニターのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="33574-111">For example, the following command retrieves data for the monitors associated with one of the core management packs:</span></span>   
   `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-ScomMonitor | export-csv "c:\monitors.csv"`