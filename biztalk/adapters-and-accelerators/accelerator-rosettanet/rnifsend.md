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
ms.openlocfilehash: 92ad9b7c0318a028b6b2f98a75eca1484014b305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282238"
---
# <a name="rnifsend"></a>RNIFSend
このサンプルは、作業 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx ファイルが、RNIF 処理用メッセージを準備し、応答側の RNIFReceive.aspx ページにメッセージを送信します。 次の ASPX ページをカスタマイズできます。  
  
- 追加または削除のパフォーマンス カウンター  
  
- データベースへのデータの書き込みや追跡機能のカスタマイズなど、ページに機能を追加します。  
  
- 検証ページを追加します。  
  
  このサンプルにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>\sdk\webapplication\rnifsender のアクセラレータです。  
  
## <a name="demonstrates"></a>使用例  
 このサンプルでは、RNIF 処理には、次の送信メッセージを準備する方法を示しています。  
  
-   MIME ヘッダーのデータの検証  
  
-   メッセージに MIME ヘッダーと MIME 境界を追加します。  
  
-   パートナーの RNIFReceive.aspx にメッセージを送信  
  
-   返されたシグナル メッセージの処理  
  
## <a name="see-also"></a>参照  
 [送信および受信 ASPX ページ](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Web アプリケーションのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)