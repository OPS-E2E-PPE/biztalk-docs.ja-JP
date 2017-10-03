---
title: "RNIFReceive |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf1253b0-ceca-4e7a-91ed-3837bd904472
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02236b1d7ff76762fffd70ed809a2cee23746372
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="rnifreceive"></a>RNIFReceive
このサンプルは、RNIF メッセージを受信し、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] パブリック プロセスによって処理するためにそれを準備する有効な [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]® [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNIFReceive.aspx ファイルを提供します。 ASPX ページをカスタマイズして、次の操作を実行できます。  
  
-   パフォーマンス カウンタの追加と削除  
  
-   機能の追加 (データベースへのデータの書き込みや追跡機能のカスタマイズなど)  
  
-   検証機能の追加  
  
 このサンプルに格納*\<ドライブ >*: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for \sdk\webapplication\rnifreceiver です。  
  
## <a name="demonstrates"></a>使用例  
 このサンプルは、以下を含み、パブリック プロセス用に着信メッセージを準備する方法を示します。  
  
-   パートナーの RNIFSend.aspx からのメッセージの受信  
  
-   MIME ヘッダーの検証  
  
-   メッセージからの MIME ヘッダーと境界の削除  
  
-   パートナーの RNIFReceive.aspx へのメッセージのルーティング  
  
-   シグナル メッセージの返信  
  
## <a name="see-also"></a>参照  
 [送信および受信 ASPX ページ](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Web アプリケーションのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)