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
ms.openlocfilehash: 4277e6b088ed136021b898e26204a63dc782a895
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008515"
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM 構成ファイルを取得する方法
管理者および開発者は、BAM 管理ユーティリティを使用して、BAM インフラストラクチャの現在の構成を取得できます。 取得した構成を使用すると、BAM のインストールを新しいサーバーに移行したり、既存の BAM を更新したりすることができます。  
  
## <a name="prerequisites"></a>前提条件  
 次に、このトピックの手順を実行するための前提条件を示します。  
  
-   構成済みの BAM データベース  
  
-   BAM プライマリ インポート データベースに対する読み取りアクセス許可  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM 構成ファイルを取得するには  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3. コマンド ライン プロンプトで、次の入力: **bm config の取得のファイル名:\<出力ファイル\>** ここで、 \<*出力ファイル*\>は置き換えられます、BAM 構成ファイルの名前です。 **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)