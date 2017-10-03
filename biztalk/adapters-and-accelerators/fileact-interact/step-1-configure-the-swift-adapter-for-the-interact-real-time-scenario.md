---
title: "手順 1: 構成用のアダプターを SWIFT、リアルタイムのシナリオを対話 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f4d3e08-611a-4af1-a3e3-957ace3b74e6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ab7f1c75baf5a974fdbc10deb1651fcce1c7d51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario"></a>手順 1: 構成用のアダプターを SWIFT、リアルタイムのシナリオの対話
次の手順では、Interact アダプターの送信ハンドラーを構成する方法について説明します。 一覧された要件を完了する必要があります、プロシージャを開始する前に[、チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)です。  
  
### <a name="to-configure-the-swift-adapter"></a>SWIFT のアダプターを構成するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで [ **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**を右クリックして**INTERACT**、] をポイント**新規**、クリックして**送信ハンドラー**です。  
  
3.  **アダプター ハンドラーのプロパティ-[対話**ダイアログ ボックスの**全般**] タブから、**ホスト名**ドロップダウン リストで、 **interacthost**、クリックして**プロパティ**です。  
  
4.  **INTERACTTransport プロパティ** ダイアログ ボックスで、**プロパティ** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**引数**|次の引数を入力: **SagMessagePartner**\<SAG で対話するクライアントのメッセージのパートナーが作成された >**注:**引数で、クライアントは SAG で構成されている MessagePartner です。|  
    |**暗号化モード**|ドロップダウン リストから選択**詳細**です。|  
    |**LogMessageBody**|ドロップダウン リストから選択`FALSE`です。 **注:**に設定した場合`TRUE`、追跡データベースにメッセージ本文を保存します。 ただし、セキュリティ上の理由から、メッセージの本文見なすことができることはありません、BAM ポータルにします。|  
    |**し**|ドロップダウン リストから選択`TRUE`です。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**[有効化]**|False|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG のヘルプを参照してください。|  
    |**[ユーザー名]**|SAG への接続に使用するユーザー名を入力します。|  
  
5.  をクリックして**OK**対話トランスポートのプロパティ ダイアログ ボックスを閉じます。  
  
6.  をクリックして**OK** INTERACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。  
  
7.  メッセージ ボックスで、をクリックして**OK**、し対話するホスト インスタンスを再起動します。  
  
## <a name="see-also"></a>参照  
 [リアルタイムのシナリオを対話します。](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [手順 1: 構成用のアダプターを SWIFT、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)   
 [手順 2: の Paramfile に SWIFTNet 構成を追加する、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-real-time-scenario.md)   
 [手順 3: が送信を作成し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [手順 4: テスト、リアルタイムのエンド ツー エンド シナリオの対話](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)