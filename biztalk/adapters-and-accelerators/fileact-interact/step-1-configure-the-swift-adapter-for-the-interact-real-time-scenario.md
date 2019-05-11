---
title: 手順 1:用に SWIFT アダプターを構成、InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f4d3e08-611a-4af1-a3e3-957ace3b74e6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08da44a01765bd1a3b1b936d77eb7cfdccae2c4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366508"
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario"></a>手順 1:用に SWIFT アダプターを構成、InterAct リアルタイム シナリオ
次の手順では、Interact アダプターの送信ハンドラーを構成する方法について説明します。 一覧された要件を完了する必要があります、プロシージャを開始する前に[チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)します。  
  
### <a name="to-configure-the-swift-adapter"></a>SWIFT アダプターを構成するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**、右クリックして**INTERACT**、 をポイント**新規**、 をクリックし、**送信ハンドラー**します。  
  
3.  **アダプター ハンドラーのプロパティ-対話** ダイアログ ボックスで、**全般** タブから、**ホスト名**ドロップダウン リストで、 **interacthost**、 をクリックし、**プロパティ**します。  
  
4.  **INTERACTTransport プロパティ** ダイアログ ボックスの 、**プロパティ** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**引数**|次の引数を入力します。**SagMessagePartner**\<SAG で対話するクライアントのメッセージのパートナーが作成された\>**に注意してください。** 引数のクライアントは、SAG で構成した MessagePartner です。|  
    |**暗号モード**|ドロップダウン リストから選択**詳細**します。|  
    |**LogMessageBody**|ドロップダウン リストから選択`FALSE`します。 **注:** 設定した場合`TRUE`、追跡データベースにメッセージ本文が維持されます。 ただし、セキュリティ上の理由から、メッセージ本文は、BAM ポータルでは表示ことはありませんすることができます。|  
    |**し**|ドロップダウン リストから選択`TRUE`します。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**[有効化]**|False|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG ヘルプを参照してください。|  
    |**[ユーザー名]**|SAG への接続に使用するユーザー名を入力します。|  
  
5.  クリックして**OK**対話トランスポートのプロパティのダイアログ ボックスを閉じます。  
  
6.  クリックして**OK** INTERACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。  
  
7.  メッセージ ボックスで、次のようにクリックします。 **OK**、し、対話のホスト インスタンスを再起動します。  
  
## <a name="see-also"></a>参照  
 [InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [ステップ 1: 用に SWIFT アダプターを構成、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)   
 [手順 2:用に Paramfile に SWIFTNet 構成を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-real-time-scenario.md)   
 [ステップ 3:作成する送信と受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [手順 4:テスト、InterAct リアルタイム エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)