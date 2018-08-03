---
title: RNIFReceive |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf1253b0-ceca-4e7a-91ed-3837bd904472
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d54b66c42fae286ec748ef560c461a22124165b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991779"
---
# <a name="rnifreceive"></a>RNIFReceive
このサンプルは、作業 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx ファイルを RNIF メッセージを受信して処理用に準備する、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パブリック プロセス。 ASPX ページをカスタマイズして、次の操作を実行できます。  
  
- パフォーマンス カウンタの追加と削除  
  
- 機能の追加 (データベースへのデータの書き込みや追跡機能のカスタマイズなど)  
  
- 検証機能の追加  
  
  このサンプルにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>\sdk\webapplication\rnifreceiver のアクセラレータです。  
  
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