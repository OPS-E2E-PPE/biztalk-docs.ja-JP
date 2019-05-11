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
ms.openlocfilehash: b2c949f87f74881da64475c74c6e26099359f925
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282253"
---
# <a name="rnifreceive"></a>RNIFReceive
このサンプルは、作業 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx ファイルを RNIF メッセージを受信して処理用に準備する、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パブリック プロセス。 次の ASPX ページをカスタマイズできます。  
  
- 追加または削除のパフォーマンス カウンター  
  
- データベースへのデータの書き込みや追跡機能のカスタマイズなど、ページに機能を追加します。  
  
- 検証ページを追加します。  
  
  このサンプルにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>\sdk\webapplication\rnifreceiver のアクセラレータです。  
  
## <a name="demonstrates"></a>使用例  
 このサンプルでは、パブリック プロセスは、次のように受信メッセージを準備する方法を示しています。  
  
-   パートナーの RNIFSend.aspx からメッセージを受信  
  
-   MIME ヘッダーの検証  
  
-   メッセージから MIME ヘッダーと境界を削除します。  
  
-   パートナーの RNIFReceive.aspx にメッセージのルーティング  
  
-   シグナル メッセージを返す  
  
## <a name="see-also"></a>参照  
 [送信および受信 ASPX ページ](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Web アプリケーションのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)