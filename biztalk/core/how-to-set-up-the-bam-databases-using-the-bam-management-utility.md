---
title: "BAM 管理ユーティリティを使用して BAM データベースを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 801338f4-b363-4f8e-b248-9c628065ded2
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9343cf9bd33f5880c564e2ec0dce72ece520ff01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-up-the-bam-databases-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM データベースを設定する方法
管理者は、通常、BizTalk Server 構成ユーティリティを使用して、BAM データベースを設定します。 代わりに BAM 管理ユーティリティ (bm.exe) を使用して、データベースを設定することもできます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件を次に示します。  
  
-   BAMPrimaryImport データベース、BAMStarSchema データベース、および BAMArchive データベースをホストする SQL Server に対する管理者権限を持っている必要があります。  
  
-   SQL Notification Services データベースを設定するには、管理者権限を持っており、ローカルの Administrators グループのメンバーであることが必要です。また、追加で構成された管理者グループ (BTS Admins グループなど) のメンバーであることも必要です。  
  
-   データベースの設定に使用する XML データを含む BAM 構成ファイルが必要です。  
  
### <a name="to-set-up-the-bam-databases-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM データベースを設定するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3.  コマンド ライン プロンプトで、次を入力: **bm セットアップ データベース ConfigFile:\<構成ファイル >**ここで、 \<*構成ファイル*> の名前に置き換えBAM 構成ファイル。 **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)