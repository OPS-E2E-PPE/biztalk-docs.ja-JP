---
title: RNIFSend |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 780f7446-56c5-40bf-95e2-25d0cff12f12
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d9aca64afee9ed979b2eee58a5f2bdafb25b461
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011603"
---
# <a name="rnifsend"></a>RNIFSend
このサンプルは、作業 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx ファイルが、RNIF 処理用メッセージを準備し、応答側の RNIFReceive.aspx ページにメッセージを送信します。 ASPX ページをカスタマイズして、次の操作を実行できます。  
  
- パフォーマンス カウンタの追加と削除  
  
- 機能の追加 (データベースへのデータの書き込みや追跡機能のカスタマイズなど)  
  
- 検証機能の追加  
  
  このサンプルにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>\sdk\webapplication\rnifsender のアクセラレータです。  
  
## <a name="demonstrates"></a>使用例  
 このサンプルは、以下のような RNIF 処理用の送信メッセージを作成する方法を示します。  
  
-   MIME ヘッダーのデータを検証する  
  
-   MIME ヘッダーと MIME 境界をページに追加する  
  
-   取引先の RNIFReceive.aspx にメッセージを送信する  
  
-   返されたシグナル メッセージを処理する  
  
## <a name="see-also"></a>参照  
 [送信および受信 ASPX ページ](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Web アプリケーションのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)