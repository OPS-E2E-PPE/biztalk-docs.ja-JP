---
title: バックアップおよび復元の後に、BAM 管理ユーティリティ構成を更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b27062b-546f-4030-983b-15d793912690
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa7d8e91ab82cc74f2af2ca0c12f79cdb0a8fcbe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970083"
---
# <a name="how-to-update-the-bam-management-utility-configuration-after-a-backup-and-restore"></a><span data-ttu-id="2f0f8-102">バックアップおよび復元の後で BAM 管理ユーティリティ構成を更新する方法</span><span class="sxs-lookup"><span data-stu-id="2f0f8-102">How to Update the BAM Management Utility Configuration After a Backup and Restore</span></span>
<span data-ttu-id="2f0f8-103">BizTalk Server 環境の変更 (バックアップおよび復元のシーケンスなど) によってサーバー名とデータベース名の組み合わせが変更された場合は、BAM 管理ユーティリティ構成ファイル (bm.exe.config) を更新してこの名前変更を反映させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f0f8-103">When the server\database name combination changes as the result of a change in your BizTalk Server environment such as a backup and restore sequence, you must update the BAM management utility configuration file (bm.exe.config) to reflect these name changes.</span></span>  
  
### <a name="to-update-the-bam-management-configuration-file-a-after-backup-and-restore"></a><span data-ttu-id="2f0f8-104">バックアップおよび復元の後で BAM 管理構成ファイルを更新するには</span><span class="sxs-lookup"><span data-stu-id="2f0f8-104">To update the BAM management configuration file a after backup and restore</span></span>  
  
1. <span data-ttu-id="2f0f8-105">クリックしてメモ帳を使用して bm.exe.config ファイルを開く**開始**、**実行**、メモ帳」と入力[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config、 をクリックして **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="2f0f8-105">Open the bm.exe.config file using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="2f0f8-106">ファイルの appSettings セクションを探し、次の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="2f0f8-106">Locate the appSettings section in the file and change the following values:</span></span>  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="oldServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
3. <span data-ttu-id="2f0f8-107">から</span><span class="sxs-lookup"><span data-stu-id="2f0f8-107">to</span></span>  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="newServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
4. <span data-ttu-id="2f0f8-108">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="2f0f8-108">Save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f0f8-109">参照</span><span class="sxs-lookup"><span data-stu-id="2f0f8-109">See Also</span></span>  
 [<span data-ttu-id="2f0f8-110">BAM データベースの管理</span><span class="sxs-lookup"><span data-stu-id="2f0f8-110">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)