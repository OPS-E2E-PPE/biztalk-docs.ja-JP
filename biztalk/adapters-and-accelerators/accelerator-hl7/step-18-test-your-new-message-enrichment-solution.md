---
title: "手順 18: 新しいメッセージの強化ソリューションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message enrichment tutorial, testing solution
ms.assetid: 233fbf79-0ab1-4064-b828-6bbbb56cbec2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca2716a5d05292f105798cf394cd05bac1104c4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-18-test-your-new-message-enrichment-solution"></a>手順 18: 新しいメッセージの強化ソリューションをテストします。
このステップでメッセージを送信するクライアント アプリケーションを使用して、ソリューションをテストする[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MLLPReceive アプリケーションが期待どおりに HL7 形式のメッセージを受け取るかどうかが表示されるとします。  
  
### <a name="to-test-your-solution"></a>ソリューションをテストするには  
  
1.  コマンド プロンプトを開きます。  
  
    > [!NOTE]
    >  手順 2 では、カスタムのインストール手順を使用し、MLLP テスト ツールがインストールされていることが必要です。 かどうか MllpReceive.exe と MllpSend.exe を含むディレクトリは、コンピューターに存在しません \MLLP ユーティリティをインストールにカスタム インストールを実行しています。 詳細については、次を参照してください。[カスタム インストールを実行する](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)です。  
  
2.  コマンド プロンプトで次のように入力します **cd \<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator の HL7\SDK\MLLP * ユーティリティ * (ここで\<。*ドライブ*> は、インストール ドライブ文字です)、キーを押します**Enter**です。  
  
3.  コマンド プロンプトで次のように入力します。 **mllpreceive/p 11000/eb 11/sb 28/cr 13**、キーを押します**Enter**です。 これにより、11000 のポートをリッスンしていると、MLLP メッセージの既定の EB、SB、および CR の文字を指定する MLLP リスナー アプリケーションを実行し、画面に受信メッセージを表示します。  
  
4.  2 番目のコマンド プロンプトを開きます。  
  
5.  コマンド プロンプトで次のように入力します。  **cd \<*ドライブ*>: \Tutorial\WSClient\bin\Debug**、を押してから**Enter**です。  
  
6.  コマンド プロンプトで次のように入力します。**クライアント john henry smith 123456789**、キーを押します**Enter**です。 Henry の John Smith の患者の名前と 123456789 サンプル社会保障番号を持つサンプル メッセージを含む Web サービスにメッセージを送信します。  
  
7.  しばらくすると、MLLPReceive アプリケーションには、MLLP の受信メッセージが表示されます。 メッセージは、次のようになります。  
  
    ```  
    MSH|^~\&|TestTrailing^Delimiters|srcFac^srcFacUid|dstApp^dstAppUid|dstFac^dstFacUid|200307092343|sec|ADT^A04|msgid2134|P|2.2PID|||123456789||smith^john  
    ```  
  
     場合は、数分後に応答を受け取りません、アプリケーション イベント ログのエラーをチェックしてトラブルシューティングを開始します。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)