---
title: ライブ データ ブックの接続文字列を更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d2702fb-637c-46db-8b62-08ae15f983ba
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2813b4ce0f448c25d75e69b1001ca006608d5993
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383625"
---
# <a name="how-to-update-the-connection-string-for-the-live-data-workbook"></a><span data-ttu-id="65274-102">ライブ データ ブックの接続文字列を更新する方法</span><span class="sxs-lookup"><span data-stu-id="65274-102">How to Update the Connection String for the Live Data Workbook</span></span>
<span data-ttu-id="65274-103">BAM プライマリ インポート データベースを別のサーバーに移動すると、新しいサーバーをポイントする BAM ライブ データ ブックの接続文字列を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65274-103">When you move the BAM Primary Import database to another server, the connection string in a BAM live data workbook must be updated to point to the new server.</span></span> <span data-ttu-id="65274-104">Excel 用 BAM アドイン使用するには、「この更新プログラムを作成しますします。</span><span class="sxs-lookup"><span data-stu-id="65274-104">You use the BAM Add-in for Excel to make this update.</span></span>  
  
### <a name="to-update-the-live-data-workbook-to-point-to-a-new-server"></a><span data-ttu-id="65274-105">新しいサーバーをポイントするライブ データ ブックを更新するには</span><span class="sxs-lookup"><span data-stu-id="65274-105">To update the live data workbook to point to a new server</span></span>  
  
1.  <span data-ttu-id="65274-106">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリックします**Microsoft Office Excel**します。</span><span class="sxs-lookup"><span data-stu-id="65274-106">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2.  <span data-ttu-id="65274-107">をクリックして、**ファイル** メニューをクリック**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="65274-107">Click the **File** menu, and then click **Open**.</span></span> <span data-ttu-id="65274-108">目的の BAM ライブ データ ブックに移動し、をクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="65274-108">Navigate to your BAM lived data workbook and click **Open**.</span></span>  
  
3.  <span data-ttu-id="65274-109">をクリックして、 **BAM**メニューで、**アドイン** タブをクリックして**BAM データベースの接続**を開く、 **BAM データベースの選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="65274-109">Click the **BAM** menu in the **Add-Ins** tab, and then click **BAM DB Connection** to open the **Select BAM Database** dialog box.</span></span>  
  
4.  <span data-ttu-id="65274-110">**SQL Server**テキスト ボックスを BAM プライマリ インポート データベースが SQL server の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="65274-110">In the **SQL Server** text box, type the name of the SQL server on which the BAM Primary Import database now resides.</span></span>  
  
5.  <span data-ttu-id="65274-111">BAM プライマリ インポート データベースを選択、**データベース名**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="65274-111">Select the BAM Primary Import database from the **Database Name** drop-down list.</span></span>  
  
6.  <span data-ttu-id="65274-112">**[OK]** をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="65274-112">Click **OK** to close the dialog box.</span></span>  
  
7.  <span data-ttu-id="65274-113">ブックを保存します。</span><span class="sxs-lookup"><span data-stu-id="65274-113">Save the workbook.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65274-114">参照</span><span class="sxs-lookup"><span data-stu-id="65274-114">See Also</span></span>  
 <span data-ttu-id="65274-115">[BAM の管理](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="65274-115">[Managing BAM](../core/managing-bam.md) </span></span>  
 [<span data-ttu-id="65274-116">Excel 用の BAM アドインを使用するための要件</span><span class="sxs-lookup"><span data-stu-id="65274-116">Requirements for Using the BAM Add-In for Excel</span></span>](../core/requirements-for-using-the-bam-add-in-for-excel.md)