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
# <a name="how-to-update-the-bam-management-utility-configuration-after-a-backup-and-restore"></a>バックアップおよび復元の後に、BAM 管理ユーティリティ構成を更新する方法
によって名前の組み合わせがバックアップと復元シーケンスなど、BizTalk Server 環境での変更の結果として変更されると、BAM 管理ユーティリティ構成ファイル (bm.exe.config) これらの名前変更を反映するようを更新する必要があります。  
  
### <a name="to-update-the-bam-management-configuration-file-a-after-backup-and-restore"></a>BAM 管理の構成の後のバックアップ ファイルを更新および復元するには  
  
1. クリックしてメモ帳を使用して bm.exe.config ファイルを開く**開始**、**実行**、メモ帳」と入力[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config、 をクリックして **[ok]**。  
  
2. ファイルの appSettings セクションを検索し、次の値を変更します。  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="oldServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
3. から  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="newServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
4. ファイルを保存します。  
  
## <a name="see-also"></a>参照  
 [BAM データベースの管理](../core/managing-bam-databases.md)