---
title: BAM 管理ユーティリティを使用して BAM データベースを設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 801338f4-b363-4f8e-b248-9c628065ded2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d01b84fb3e538ee81351cbcfe380d893c5f0cc7b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334091"
---
# <a name="how-to-set-up-the-bam-databases-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM データベースを設定する方法
通常、管理者は、BAM データベースを設定する、BizTalk Server 構成ユーティリティを使用します。 別の方法として、BAM 管理ユーティリティ (bm.exe) を使用するには、データベースを設定します。  
  
## <a name="prerequisites"></a>前提条件  
 次に、このトピックの手順を実行するための前提条件を示します。  
  
-   管理者のアクセス許可は、BAMPrimaryImport、bamstarschema データベース、および BAMArchive データベースをホストする SQL server が必要です。  
  
-   SQL Notification Services データベースを設定するにする必要があります管理者権限を持っていると、ローカルの administrators グループのメンバーであるだけでなく、BTS Admins グループなど、構成されているすべての追加の管理者グループのメンバーであります。  
  
-   元のデータベースを設定する XML データを含む BAM 構成ファイルが必要です。  
  
### <a name="to-set-up-the-bam-databases-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM データベースを設定するには  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. 移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。  
  
3. コマンド ライン プロンプトで、次の入力: **bm セットアップ データベース ConfigFile:\<構成ファイル\>** ここで、 \<*構成ファイル*\>、BAM 構成ファイルの名前は置き換えられます。 **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)