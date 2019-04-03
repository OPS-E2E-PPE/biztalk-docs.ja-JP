---
title: 受信場所のポーリング間隔をバッチ処理 SQL アダプターの設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- polling interval [receive adapters]
- SQL adapters, polling interval
- receive locations, polling interval
- SQL adapters, receive locations
- receive locations, SQL adapters
ms.assetid: 9053b20d-145a-4445-b414-c0482cf975a0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: caa2c97170ff374e9acf8c1d3d4ebc7258ad69ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005051"
---
# <a name="setting-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a>バッチ処理 SQL アダプター受信場所のポーリング間隔の設定
間隔を設定できます、ポーリングでバッチ処理 SQL アダプター受信場所 (**BatchControlMessageRecvLoc**) の開発と運用環境のコンピューターでそれぞれ異なる。 開発サーバーでは、ポーリング間隔は 30 秒の既定値のままにして、アグリーメントのバッチ処理オーケストレーションをすばやくアクティブ化できるようにすることをお勧めします。 ただし実稼働サーバーでは、30 秒に設定するとパフォーマンスに影響する場合があります。 バッチをアクティブ化した後、ポーリング間隔を 5 分などの高い値に設定することをお勧めします。  
  
 パーティの詳細については、[管理パーティ](../core/managing-parties.md)を参照してください。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-set-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a>バッチ処理 SQL アダプタ受信場所のポーリング間隔を設定するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**BizTalk EDI アプリケーション**、 をクリックし、**受信場所**します。 右クリックして**BatchControlMessageRecvLoc**、 をクリック**プロパティ**します。  
  
2. **受信場所のプロパティ**] ダイアログ ボックスで、**トランスポート**セクションで、[**構成**します。  
  
3. **SQL トランスポートのプロパティ** ダイアログ ボックスの値を変更**のポーリング間隔**目的の値を「30」の既定値から。 実稼働サーバーの推奨値は "5" です。  
  
4. 値を変更**ポーリング単位**の既定値から**秒**に**分**します。  
  
5. をクリックして**OK**、順にクリックします**OK**もう一度  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションの管理](../core/managing-edi-and-as2-solutions.md)