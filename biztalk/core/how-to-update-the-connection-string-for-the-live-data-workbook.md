---
title: ライブ データ ブックの接続文字列を更新する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 60de5d1ae904bdefffcf490e3a39d000b28a341d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255314"
---
# <a name="how-to-update-the-connection-string-for-the-live-data-workbook"></a><span data-ttu-id="e823e-102">ライブ データ ブックの接続文字列を更新する方法</span><span class="sxs-lookup"><span data-stu-id="e823e-102">How to Update the Connection String for the Live Data Workbook</span></span>
<span data-ttu-id="e823e-103">BAM プライマリ インポート データベースを別のサーバーに移動するときには、BAM ライブ データ ブックの接続文字列を、新しいサーバーを示すように更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e823e-103">When you move the BAM Primary Import database to another server, the connection string in a BAM live data workbook must be updated to point to the new server.</span></span> <span data-ttu-id="e823e-104">この更新には Excel 用 BAM アドインを使用します。</span><span class="sxs-lookup"><span data-stu-id="e823e-104">You use the BAM Add-in for Excel to make this update.</span></span>  
  
### <a name="to-update-the-live-data-workbook-to-point-to-a-new-server"></a><span data-ttu-id="e823e-105">新しいサーバーを示すようライブ データ ブックを更新するには</span><span class="sxs-lookup"><span data-stu-id="e823e-105">To update the live data workbook to point to a new server</span></span>  
  
1.  <span data-ttu-id="e823e-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリック**Microsoft Office Excel**です。</span><span class="sxs-lookup"><span data-stu-id="e823e-106">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2.  <span data-ttu-id="e823e-107">クリックして、**ファイル** メニューをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="e823e-107">Click the **File** menu, and then click **Open**.</span></span> <span data-ttu-id="e823e-108">目的の BAM ライブ データ ブックに移動し、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="e823e-108">Navigate to your BAM lived data workbook and click **Open**.</span></span>  
  
3.  <span data-ttu-id="e823e-109">をクリックして、 **BAM**でメニュー、**アドイン** タブをクリックして**BAM データベースの接続**を開くには、 **BAM データベースの** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e823e-109">Click the **BAM** menu in the **Add-Ins** tab, and then click **BAM DB Connection** to open the **Select BAM Database** dialog box.</span></span>  
  
4.  <span data-ttu-id="e823e-110">**SQL Server**  ボックスに、BAM プライマリ インポート データベースを今すぐ SQL server の名前が存在する型。</span><span class="sxs-lookup"><span data-stu-id="e823e-110">In the **SQL Server** text box, type the name of the SQL server on which the BAM Primary Import database now resides.</span></span>  
  
5.  <span data-ttu-id="e823e-111">BAM プライマリ インポート データベースを選択して、**データベース名**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="e823e-111">Select the BAM Primary Import database from the **Database Name** drop-down list.</span></span>  
  
6.  <span data-ttu-id="e823e-112">**[OK]** をクリックして、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e823e-112">Click **OK** to close the dialog box.</span></span>  
  
7.  <span data-ttu-id="e823e-113">ブックを保存します。</span><span class="sxs-lookup"><span data-stu-id="e823e-113">Save the workbook.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e823e-114">参照</span><span class="sxs-lookup"><span data-stu-id="e823e-114">See Also</span></span>  
 <span data-ttu-id="e823e-115">[BAM の管理](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="e823e-115">[Managing BAM](../core/managing-bam.md) </span></span>  
 [<span data-ttu-id="e823e-116">Excel 用 BAM アドインを使用するための要件</span><span class="sxs-lookup"><span data-stu-id="e823e-116">Requirements for Using the BAM Add-In for Excel</span></span>](../core/requirements-for-using-the-bam-add-in-for-excel.md)