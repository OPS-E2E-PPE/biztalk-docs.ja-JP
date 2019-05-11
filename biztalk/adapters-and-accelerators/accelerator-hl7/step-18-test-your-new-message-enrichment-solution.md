---
title: 手順 18:新しいメッセージ強化ソリューションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, testing solution
ms.assetid: 233fbf79-0ab1-4064-b828-6bbbb56cbec2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8f57aeb039d2ff4e33f2bfcf14a2d4cf2257f27
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288744"
---
# <a name="step-18-test-your-new-message-enrichment-solution"></a>手順 18:新しいメッセージ強化ソリューションをテストします。
この手順でメッセージを送信する WSClient アプリケーションを使用して、ソリューションをテストする[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と MLLPReceive アプリケーションが期待どおりに、HL7 形式のメッセージを受け取るかどうかが表示されます。  
  
### <a name="to-test-your-solution"></a>ソリューションをテストします。  
  
1.  コマンド プロンプトを開きます。  
  
    > [!NOTE]
    >  手順 2 では、カスタム インストールの手順を使用して、MLLP テスト ツールがインストールされていることが必要です。 MllpReceive.exe と MllpSend.exe を含むディレクトリがコンピューターに存在しない \MLLP ユーティリティのインストールをカスタム インストールを実行することによってかどうか。 詳しくは、次を参照してください。[カスタム インストールを実行する](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)します。  
  
2.  コマンド プロンプトで「 **cd \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータ**(場所\<*ドライブ*\>インストールのドライブ文字)、およびキーを押します **」と入力**します。  
  
3.  コマンド プロンプトで「 **mllpreceive/p 11000/eb 11/sb 28/cr 13**、押します **」と入力**します。 これにより、MLLP リスナー アプリケーション ポート 11000 にリッスンしていると、MLLP メッセージの既定 EB、SB、CR 文字を指定することを実行し、他の画面に受信メッセージを表示します。  
  
4.  2 番目のコマンド プロンプトを開きます。  
  
5.  コマンド プロンプトで「 **cd \<*ドライブ*\>: \Tutorial\WSClient\bin\Debug**キー押しますと **」と入力**します。  
  
6.  コマンド プロンプトで「 **wsclient john henry smith 123456789**、押します **」と入力**します。 John Henry Smith の患者の名前と 123456789 のサンプルの社会保障番号を示すサンプル メッセージを含む Web サービスにメッセージを送信します。  
  
7.  しばらくすると、MLLPReceive アプリケーション MLLP の受信メッセージが表示されます。 メッセージは、次のようになります。  
  
    ```  
    MSH|^~\&|TestTrailing^Delimiters|srcFac^srcFacUid|dstApp^dstAppUid|dstFac^dstFacUid|200307092343|sec|ADT^A04|msgid2134|P|2.2PID|||123456789||smith^john  
    ```  
  
     数分後に、対応を受けられないと場合、は、アプリケーションのイベント ログ エラーを確認し、トラブルシューティングを開始する必要があります。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)