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
ms.openlocfilehash: b33d86a80f87991bf0d22f0daac3c15ccc83f841
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398646"
---
# <a name="how-to-update-the-bam-management-utility-configuration-after-a-backup-and-restore"></a><span data-ttu-id="790f3-102">バックアップおよび復元の後に、BAM 管理ユーティリティ構成を更新する方法</span><span class="sxs-lookup"><span data-stu-id="790f3-102">How to Update the BAM Management Utility Configuration After a Backup and Restore</span></span>
<span data-ttu-id="790f3-103">によって名前の組み合わせがバックアップと復元シーケンスなど、BizTalk Server 環境での変更の結果として変更されると、BAM 管理ユーティリティ構成ファイル (bm.exe.config) これらの名前変更を反映するようを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="790f3-103">When the server\database name combination changes as the result of a change in your BizTalk Server environment such as a backup and restore sequence, you must update the BAM management utility configuration file (bm.exe.config) to reflect these name changes.</span></span>  
  
### <a name="to-update-the-bam-management-configuration-file-a-after-backup-and-restore"></a><span data-ttu-id="790f3-104">BAM 管理の構成の後のバックアップ ファイルを更新および復元するには</span><span class="sxs-lookup"><span data-stu-id="790f3-104">To update the BAM management configuration file a after backup and restore</span></span>  
  
1. <span data-ttu-id="790f3-105">クリックしてメモ帳を使用して bm.exe.config ファイルを開く**開始**、**実行**、メモ帳」と入力[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config、 をクリックして **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="790f3-105">Open the bm.exe.config file using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="790f3-106">ファイルの appSettings セクションを検索し、次の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="790f3-106">Locate the appSettings section in the file and change the following values:</span></span>  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="oldServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
3. <span data-ttu-id="790f3-107">から</span><span class="sxs-lookup"><span data-stu-id="790f3-107">to</span></span>  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="newServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
4. <span data-ttu-id="790f3-108">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="790f3-108">Save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790f3-109">参照</span><span class="sxs-lookup"><span data-stu-id="790f3-109">See Also</span></span>  
 [<span data-ttu-id="790f3-110">BAM データベースの管理</span><span class="sxs-lookup"><span data-stu-id="790f3-110">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)