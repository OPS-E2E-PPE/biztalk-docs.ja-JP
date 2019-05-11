---
title: BAM 管理ユーティリティを使用して BAM 構成ファイルを取得する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67ce5e0c-467a-486c-8eec-217a2a26d7b4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80974231b839225652721e8c64aaf35a0f1369f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384093"
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM 構成ファイルを取得する方法
管理者および開発者は、BAM インフラストラクチャの現在の構成を取得するのに、BAM 管理ユーティリティを使用することができます。 変更して、既存の BAM のインストールを更新するために使用または新しいサーバーに、BAM のインストールを移行する取得した構成を使用できます。  
  
## <a name="prerequisites"></a>前提条件  
 次に、このトピックの手順を実行するための前提条件を示します。  
  
-   構成済みの BAM データベース  
  
-   BAM プライマリ インポート データベースの読み取りアクセス許可  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM 構成ファイルを取得するには  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. 移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。  
  
3. コマンド ライン プロンプトで、次の入力: **bm config の取得のファイル名:\<出力ファイル\>** ここで、 \<*出力ファイル*\>は置き換えられます、BAM 構成ファイルの名前です。 **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)