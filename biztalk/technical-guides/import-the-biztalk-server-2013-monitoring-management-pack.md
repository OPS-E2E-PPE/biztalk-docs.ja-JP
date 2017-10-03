---
title: "BizTalk Server 2013 の監視管理パックのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bee2bfe9-4eb0-46d4-8eee-75182202080c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c6dff55cce17d9b9159a8eca754f91373621929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="import-the-biztalk-server-2013-monitoring-management-pack"></a>BizTalk Server 2013 の監視管理パックをインポートします。
管理パックをインポートする方法については、管理パックをインポートする方法を参照してください[Operations Manager 2007 R2 または 2012](http://go.microsoft.com/fwlink/?LinkId=142351) (http://go.microsoft.com/fwlink/?LinkId=142351)。 後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックのインポートは、次の手順を実行して初期構成を完了します。  
  
### <a name="to-configure-the-management-pack"></a>管理パックを構成するには  
  
1.  新しい管理パックを作成する上書きやその他のカスタマイズを格納します。  
  
2.  エージェント プロキシ設定を有効にするには、次の手順を実行します。  
  
    1.  オペレーション コンソールを開き、管理 をクリック をクリックします。  
  
    2.  ペインで、管理者、クリックして**エージェントで管理**です。  
  
    3.  一覧内のエージェントをダブルクリックします。  
  
    4.  [セキュリティ] タブで、**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出**です。  
  
    5.  BizTalk Server にインストールされているエージェントごとに手順 3 ~ 4 を繰り返します。