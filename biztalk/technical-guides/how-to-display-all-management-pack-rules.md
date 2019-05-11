---
title: すべての管理パックのルールを表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7fdec550-6713-4f5f-8c04-d9218bf2df3c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c22102080d5852ab838ce8fa3ce1d421e9a42900
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253503"
---
# <a name="how-to-display-all-management-pack-rules"></a><span data-ttu-id="42f4c-102">すべての管理パックのルールを表示する方法</span><span class="sxs-lookup"><span data-stu-id="42f4c-102">How to Display All Management Pack Rules</span></span>
<span data-ttu-id="42f4c-103">インポートした管理パックのルールの一覧を表示するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="42f4c-103">Use the following procedure to display a list of rules for the management packs that you imported.</span></span> <span data-ttu-id="42f4c-104">Office Excel では、ルールの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="42f4c-104">The list of rules can be viewed in Office Excel.</span></span>  
  
### <a name="to-display-management-pack-rules"></a><span data-ttu-id="42f4c-105">管理パックのルールを表示するには</span><span class="sxs-lookup"><span data-stu-id="42f4c-105">To display management pack rules</span></span>  
  
1.  <span data-ttu-id="42f4c-106">管理サーバーで次のようにクリックします。**プログラム**、 をクリックし、 **System Center**します。</span><span class="sxs-lookup"><span data-stu-id="42f4c-106">In your management server, click **Programs**, and then click **System Center**.</span></span>  
  
2.  <span data-ttu-id="42f4c-107">クリックして**コマンド シェル**します。</span><span class="sxs-lookup"><span data-stu-id="42f4c-107">Click **Command Shell**.</span></span>  
  
3.  <span data-ttu-id="42f4c-108">コマンド シェルでは、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="42f4c-108">In the Command Shell, type the following command:</span></span>   
    `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | export-csv "c:\rules.csv"`  
  
4.  <span data-ttu-id="42f4c-109">.Csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="42f4c-109">A .csv file is created.</span></span> <span data-ttu-id="42f4c-110">Office Excel で .csv ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="42f4c-110">You can open the .csv file in Office Excel.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="42f4c-111">Office Excel で .csv ファイルをテキスト ファイルに指定する必要する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f4c-111">In Office Excel, you may be required to specify that the .csv file is a text file.</span></span>