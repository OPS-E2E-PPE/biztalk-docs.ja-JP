---
title: バックアップと復元の後に BAM 管理ユーティリティ構成を更新する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: cf316e7275b3db47b02a7f09ed5d2a66571c4de1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286674"
---
# <a name="how-to-update-the-bam-management-utility-configuration-after-a-backup-and-restore"></a>バックアップおよび復元の後で BAM 管理ユーティリティ構成を更新する方法
BizTalk Server 環境の変更 (バックアップおよび復元のシーケンスなど) によってサーバー名とデータベース名の組み合わせが変更された場合は、BAM 管理ユーティリティ構成ファイル (bm.exe.config) を更新してこの名前変更を反映させる必要があります。  
  
### <a name="to-update-the-bam-management-configuration-file-a-after-backup-and-restore"></a>バックアップおよび復元の後で BAM 管理構成ファイルを更新するには  
  
1.  クリックしてメモ帳を使用して bm.exe.config ファイルを開く**開始**をクリックすると、**実行**、メモ帳」と入力[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config、クリックして **[ok]** です。  
  
2.  ファイルの appSettings セクションを探し、次の値を変更します。  
  
    ```  
    <!-- Default server and database for bm.exe. -->  
    <add key="DefaultServer" value="oldServerName" />  
    <add key="DefaultDatabase" value="BAMPrimaryImport" />  
    ```  
  
3.  から  
  
    ```  
    <!-- Default server and database for bm.exe. -->  
    <add key="DefaultServer" value="newServerName" />  
    <add key="DefaultDatabase" value="BAMPrimaryImport" />  
    ```  
  
4.  ファイルを保存します。  
  
## <a name="see-also"></a>参照  
 [BAM データベースの管理](../core/managing-bam-databases.md)