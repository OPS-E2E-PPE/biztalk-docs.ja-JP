---
title: "インストールのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing installation
- installing, testing installation
ms.assetid: db27a75c-db7f-46ff-b8ef-2624ff18dcc8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7fc94930ba5ff0851114e36d728ee7f3ffb73ab
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="testing-your-installation"></a>インストールのテスト
設定することができます、[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]テスト、エンド ツー エンド チュートリアルを手動で実行して、またはエンド ツー エンド チュートリアル プログラムを実行してインストールします。 プログラムを実行するをクリックするか、 **Launch Tutorial**セットアップ中にボタンをクリックしてしたり、C:\Program files \microsoft BizTalk で EndToEndTutorial.exe を実行\<バージョン\>HL7\SDK\ のアクセラレータエンド ツー エンド チュートリアル フォルダー (インストールと構成を実行している)。 これらの自動化されたアクションのいずれかの操作はチュートリアルを実行して、手動で実行する同じセットアップ手順を実行します。 エンド ツー エンド チュートリアル プログラムは次のとおり  
  
-   MSH と確認のスキーマを展開します。  
  
-   Version 2.3.1 の一般的なスキーマを展開します。  
  
-   ADT スキーマを展開します。  
  
-   作成、Tutorial_1WayReceive 受信ポート  
  
-   作成、Tutorial_MLLPReceive 受信場所  
  
-   作成、Tutorial_BTAHL7PickUp 受信ポート  
  
-   作成、Tutorial_FileReceiveLoc 受信場所  
  
-   Tutorial_sendAck_ADT 送信ポートが作成されます。  
  
-   Tutorial_sendMsg_RX 送信ポートが作成されます。  
  
-   Tutorial_BTAHL7Drop 送信ポートが作成されます。  
  
-   Tutorial_MLLPSend 送信ポートが作成されます。  
  
-   Tutorial_ADTSystem パーティを作成します。  
  
-   Tutorial_RXSystem パーティを作成します。  
  
-   Tutorial_HISystem パーティを作成します。  
  
-   BizTalk サービスを再起動します。  
  
 エンド ツー エンド チュートリアル プログラムを実行した場合は、事前に定義されたフォルダーに HL7 のテスト インスタンスを削除できます。 フォルダーに関連付けられている受信パイプラインは、メッセージを取得し、それを処理します。 フィルターに基づいて、送信パイプラインは、コピー先のフォルダーにドキュメントをルーティングします。 単純な「ラウンド トリップ」がこの基本的な構成要素の実行、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) エンジンし、インストールされていることを確認します。  
  
### <a name="to-test-your-installation"></a>インストールをテストするには  
  
1.  使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for HL7\SDK\End エンドツー エンド チュートリアル フォルダーです。  
  
2.  右クリックし、 **TutorialSampleInstance.txt**ファイルを開き、をクリックして**コピー**です。  
  
3.  使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド Tutorial\Tutorial_ のアクセラレータBTAHL7PickUp フォルダーです。  
  
4.  フォルダーを右クリックし、をクリックして**貼り付け**です。  
  
5.  使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド Tutorial\Tutorial_ のアクセラレータBTAHL7Drop フォルダーです。  
  
     かどうか、インストールが正常に処理済みのインスタンスが表示される場合を確認することができます、 **Tutorial_BTAHL7Drop**としてフォルダー \< *Guid*\>.txt です。  
  
 次の手順に進む[、チュートリアルを使用する準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)です。