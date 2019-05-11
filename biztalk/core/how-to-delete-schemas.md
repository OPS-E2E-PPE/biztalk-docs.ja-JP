---
title: スキーマを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b438d030-c4da-403b-ae10-abb005423651
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28a09a5f209e71ce11f1358ecbe32bfb36dea144
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385305"
---
# <a name="how-to-delete-schemas"></a><span data-ttu-id="58433-102">スキーマを削除する方法</span><span class="sxs-lookup"><span data-stu-id="58433-102">How to Delete Schemas</span></span>
<span data-ttu-id="58433-103">だけでなく、BizTalk プロジェクトのスキーマを除外する、スキーマをハード_ディスクからも完全に削除する必要になります。</span><span class="sxs-lookup"><span data-stu-id="58433-103">Sometimes you might want to not only exclude a schema from its BizTalk project, but also completely remove the schema from your hard disk.</span></span> <span data-ttu-id="58433-104">これは、スキーマの除外ではなく、削除と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="58433-104">This is known as deleting, as opposed to excluding, a schema.</span></span> <span data-ttu-id="58433-105">このトピックでは、スキーマを削除に必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="58433-105">This topic describes the steps required to delete a schema.</span></span>  
  
### <a name="to-delete-a-schema"></a><span data-ttu-id="58433-106">スキーマを削除するには</span><span class="sxs-lookup"><span data-stu-id="58433-106">To delete a schema</span></span>  
  
1.  <span data-ttu-id="58433-107">ソリューション エクスプ ローラーで、削除、およびクリックするスキーマを右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="58433-107">In Solution Explorer, right-click the schema that you want to delete, and then click **Delete**.</span></span>  
  
2.  <span data-ttu-id="58433-108">確認のダイアログ ボックスで **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58433-108">In the confirmation dialog box, click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58433-109">削除したスキーマは、ファイル システムから完全に削除慎重、そのため、ファイルを定期的にバックアップを選択します。</span><span class="sxs-lookup"><span data-stu-id="58433-109">Deleted schemas are permanently removed from the file system, so proceed cautiously and back up your files regularly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58433-110">参照</span><span class="sxs-lookup"><span data-stu-id="58433-110">See Also</span></span>  
 [<span data-ttu-id="58433-111">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="58433-111">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)