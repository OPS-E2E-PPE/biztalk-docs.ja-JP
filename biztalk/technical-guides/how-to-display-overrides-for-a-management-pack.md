---
title: 管理パックの上書きを表示する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8261a514-b4c4-4e6b-ac35-40a3e3e090e0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a28c4ab2ef8f82fdd770203816239ad78e74418e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297690"
---
# <a name="how-to-display-overrides-for-a-management-pack"></a><span data-ttu-id="173fa-102">管理パックの上書きを表示する方法</span><span class="sxs-lookup"><span data-stu-id="173fa-102">How to Display Overrides for a Management Pack</span></span>
<span data-ttu-id="173fa-103">管理パックの上書きを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="173fa-103">To display overrides for a management pack, use the following procedure.</span></span>  
  
### <a name="to-display-overrides-for-a-management-pack"></a><span data-ttu-id="173fa-104">管理パックの上書きを表示するには</span><span class="sxs-lookup"><span data-stu-id="173fa-104">To display overrides for a management pack</span></span>  
  
1.  <span data-ttu-id="173fa-105">管理サーバーで、をクリックして**プログラム**、クリックして**System Center**です。</span><span class="sxs-lookup"><span data-stu-id="173fa-105">In your management server, click **Programs**, and then click **System Center**.</span></span>  
  
2.  <span data-ttu-id="173fa-106">をクリックして**コマンド シェル**です。</span><span class="sxs-lookup"><span data-stu-id="173fa-106">Click **Command Shell**.</span></span>  
  
3.  <span data-ttu-id="173fa-107">コマンド シェルでは、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="173fa-107">In the Command Shell, type the following command:</span></span>   
    `$mp = get-scommanagementpack -DisplayName "Operations Manager Internal Library"`   
    `$mp.GetOverrides()`  
  
4.  <span data-ttu-id="173fa-108">.Csv ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="173fa-108">A .csv file is created.</span></span> <span data-ttu-id="173fa-109">この .csv ファイルは、Office Excel で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="173fa-109">The .csv file can be opened in Office Excel.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="173fa-110">Office Excel では、.csv ファイルは、テキスト ファイルを指定する必要する必要があります。</span><span class="sxs-lookup"><span data-stu-id="173fa-110">In Office Excel, you may be required to specify that the .csv file is a text file.</span></span>  
  
 <span data-ttu-id="173fa-111">たとえば、次のコマンドは、コア管理パックのいずれかの上書きを表示します。</span><span class="sxs-lookup"><span data-stu-id="173fa-111">For example, the following command displays the overrides for one of the core management packs:</span></span>   
`$mp = get-scommanagementpack -DisplayName "Contoso.BizTalk.Overrides.mp"`  
`$mp.GetOverrides()`