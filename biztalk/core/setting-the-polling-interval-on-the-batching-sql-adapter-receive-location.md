---
title: バッチ処理 SQL アダプターのポーリング間隔の設定の受信場所 |Microsoft ドキュメント
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
ms.openlocfilehash: 830cafc89c87ce84048bad8f6e4e9f2feb34f565
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269690"
---
# <a name="setting-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a>バッチ処理 SQL アダプター受信場所のポーリング間隔の設定
設定できます、ポーリング間隔でバッチ処理 SQL アダプター受信場所 (**BatchControlMessageRecvLoc**) の開発と実稼働のコンピューターでそれぞれ異なる。 開発サーバーでは、ポーリング間隔は 30 秒の既定値のままにして、アグリーメントのバッチ処理オーケストレーションをすばやくアクティブ化できるようにすることをお勧めします。 ただし実稼働サーバーでは、30 秒に設定するとパフォーマンスに影響する場合があります。 バッチをアクティブ化した後、ポーリング間隔を 5 分などの高い値に設定することをお勧めします。  
  
 パーティの詳細については、次を参照してください。[を管理するパーティ](../core/managing-parties.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-set-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a>バッチ処理 SQL アダプタ受信場所のポーリング間隔を設定するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**BizTalk EDI アプリケーション**、クリックして**受信場所**です。 右クリック**BatchControlMessageRecvLoc**、 をクリック**プロパティ**です。  
  
2.  **受信場所のプロパティ**] ダイアログ ボックスで、**トランスポート**セクションで、[**構成**です。  
  
3.  **SQL トランスポートのプロパティ** ダイアログ ボックスの値を変更**のポーリング間隔**目的の値を「30」の既定値からです。 実稼働サーバーの推奨値は "5" です。  
  
4.  値を変更**ポーリング単位**の既定値から**秒**に**分**です。  
  
5.  をクリックして **[ok]**、順にクリック**OK**再度  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションの管理](../core/managing-edi-and-as2-solutions.md)