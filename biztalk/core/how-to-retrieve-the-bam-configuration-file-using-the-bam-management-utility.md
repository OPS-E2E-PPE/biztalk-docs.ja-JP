---
title: "BAM 管理ユーティリティを使用して BAM 構成ファイルを取得する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67ce5e0c-467a-486c-8eec-217a2a26d7b4
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eb7dee70d3a5b8dc7226203df9f48aefe1d5fc0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM 構成ファイルを取得する方法
管理者および開発者は、BAM 管理ユーティリティを使用して、BAM インフラストラクチャの現在の構成を取得できます。 取得した構成を使用すると、BAM のインストールを新しいサーバーに移行したり、既存の BAM を更新したりすることができます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件を次に示します。  
  
-   構成済みの BAM データベース  
  
-   BAM プライマリ インポート データベースに対する読み取りアクセス許可  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM 構成ファイルを取得するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3.  コマンド ライン プロンプトで、次を入力: **bm get config ファイル名:\<出力ファイル >**ここで、 \<*出力ファイル*> は、BAM 構成の名前に置換ファイルです。 **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)