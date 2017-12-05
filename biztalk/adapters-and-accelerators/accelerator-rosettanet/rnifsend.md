---
title: "RNIFSend |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 780f7446-56c5-40bf-95e2-25d0cff12f12
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73cf8a832e495944ce7c891421645ae2566e3575
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="rnifsend"></a>RNIFSend
このサンプルには、RNIF 処理用のメッセージを作成して応答側の RNIFReceive.aspx ページに送信する作業用の [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx ファイルがあります。 ASPX ページをカスタマイズして、次の操作を実行できます。  
  
-   パフォーマンス カウンタの追加と削除  
  
-   機能の追加 (データベースへのデータの書き込みや追跡機能のカスタマイズなど)  
  
-   検証機能の追加  
  
 このサンプルに格納*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>\sdk\webapplication\rnifsender のアクセラレータです。  
  
## <a name="demonstrates"></a>使用例  
 このサンプルは、以下のような RNIF 処理用の送信メッセージを作成する方法を示します。  
  
-   MIME ヘッダーのデータを検証する  
  
-   MIME ヘッダーと MIME 境界をページに追加する  
  
-   取引先の RNIFReceive.aspx にメッセージを送信する  
  
-   返されたシグナル メッセージを処理する  
  
## <a name="see-also"></a>参照  
 [送信および受信 ASPX ページ](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Web アプリケーションのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)