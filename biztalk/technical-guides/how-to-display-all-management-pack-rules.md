---
title: 管理パックのすべてのルールを表示する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 08ec94eb3adb87bf6feaff032e00a61bc9b0fead
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298218"
---
# <a name="how-to-display-all-management-pack-rules"></a><span data-ttu-id="c269d-102">管理パックのすべてのルールを表示する方法</span><span class="sxs-lookup"><span data-stu-id="c269d-102">How to Display All Management Pack Rules</span></span>
<span data-ttu-id="c269d-103">次の手順を使用すると、インポートした管理パックのルールの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c269d-103">Use the following procedure to display a list of rules for the management packs that you imported.</span></span> <span data-ttu-id="c269d-104">Office Excel では、ルールの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c269d-104">The list of rules can be viewed in Office Excel.</span></span>  
  
### <a name="to-display-management-pack-rules"></a><span data-ttu-id="c269d-105">管理パックのルールを表示するには</span><span class="sxs-lookup"><span data-stu-id="c269d-105">To display management pack rules</span></span>  
  
1.  <span data-ttu-id="c269d-106">管理サーバーで、をクリックして**プログラム**、クリックして**System Center**です。</span><span class="sxs-lookup"><span data-stu-id="c269d-106">In your management server, click **Programs**, and then click **System Center**.</span></span>  
  
2.  <span data-ttu-id="c269d-107">をクリックして**コマンド シェル**です。</span><span class="sxs-lookup"><span data-stu-id="c269d-107">Click **Command Shell**.</span></span>  
  
3.  <span data-ttu-id="c269d-108">コマンド シェルでは、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c269d-108">In the Command Shell, type the following command:</span></span>   
    `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | export-csv "c:\rules.csv"`  
  
4.  <span data-ttu-id="c269d-109">.Csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c269d-109">A .csv file is created.</span></span> <span data-ttu-id="c269d-110">Office Excel では、.csv ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="c269d-110">You can open the .csv file in Office Excel.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c269d-111">Office Excel では、.csv ファイルは、テキスト ファイルを指定する必要する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c269d-111">In Office Excel, you may be required to specify that the .csv file is a text file.</span></span>