---
title: '手順 1: InterAct ストアと転送シナリオ SWIFT のアダプターを構成する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03b81599-bd26-44dc-9cf3-73868248764c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f54effeeeb83d7a863298dcac4118ab1495ce3c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966086"
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario"></a>手順 1: InterAct ストアと転送シナリオ SWIFT のアダプターを構成します。
この手順を開始する前に行う必要があります[、チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)です。  
  
### <a name="to-configure-the-swift-adapter"></a>SWIFT のアダプターを構成するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk Server 管理コンソールを展開し、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**を右クリックして**INTERACT**、 をポイント**新規**、クリックして**送信ハンドラー**です。  
  
3.  **アダプター ハンドラーのプロパティ-[対話**ダイアログ ボックスの**全般**] タブから、**ホスト名**ドロップダウン リストで、 **interacthost**、クリックして**プロパティ**です。  
  
4.  **トランスポートのプロパティの対話** ダイアログ ボックスで、**プロパティ** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**引数**|次の引数を入力: – SagMessagePartner \<SAG で対話するクライアントのメッセージのパートナーが作成された\>**注:** 引数で、クライアントは SAG で構成されている MessagePartner です。|  
    |**暗号化モード**|ドロップダウン リストから選択**詳細**です。|  
    |**LogMessageBody**|ドロップダウン リストから選択**FALSE**です。 **注:** を TRUE に設定する場合、BizTalk 追跡データベースでメッセージ本文が保持されます。 ただし、セキュリティ上の理由から、メッセージの本文見なすことができることはありません、BAM ポータルにします。|  
    |**し**|ドロップダウン リストから選択**TRUE**です。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**[有効化]**|False : |  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG のヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
  
5.  をクリックして**OK**対話トランスポートのプロパティ ダイアログ ボックスを閉じます。  
  
6.  をクリックして**OK** INTERACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。  
  
7.  メッセージ ボックスで、をクリックして**OK**、し対話するホスト インスタンスを再起動します。  
  
## <a name="see-also"></a>参照  
 [ストアと順方向 (プッシュ) シナリオを対話します。](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [手順 2: SWIFTNet の構成を追加、Paramfile InterAct ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)   
 [手順 3: 送信ポートを作成し、対話ストアと転送シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [手順 4: InterAct ストア アンド フォワード エンド ツー エンド シナリオをテストする](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)