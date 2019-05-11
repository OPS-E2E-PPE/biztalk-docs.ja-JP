---
title: 手順 1:FileAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18653322-b748-4954-93f7-9a7a39e406f8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40426064973a74c96d7ce3be2fd681b69e3d7f5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366487"
---
# <a name="step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario"></a>手順 1:FileAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成します。
完全な[チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)この手順を開始する前にします。
  
## <a name="configure-the-swift-adapter"></a>SWIFT アダプターを構成します。  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**、右クリックして**FILEACT**、 をポイント**新規**、 をクリックし、**送信ハンドラー**します。  
  
3.  **FILEACT – アダプター HandlerProperties**  ダイアログ ボックスの 、**全般** タブから、**ホスト名**ドロップダウン リストで、 **fileacthost**、 をクリックし、**プロパティ**します。  
  
4.  **FILEACT トランスポートのプロパティ** ダイアログ ボックスの 、**プロパティ** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**引数**|次の引数を入力: - SagMessagePartner \<SAG で Fileact クライアント メッセージのパートナーが作成される\>**に注意してください。** 引数のクライアントは、SAG で構成した MessagePartner です。|  
    |**暗号モード**|ドロップダウン リストから選択**詳細**します。|  
    |**FACryptoMode**|ドロップダウン リストから選択**詳細**します。|  
    |**し**|ドロップダウン リストから選択**TRUE**します。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**[有効化]**|False|  
    |**イベントのエンドポイント**|適切な SAG エンドポイントを入力します。|  
    |**PhysicalFolderName**|サーバー上のフォルダーの名前を入力します。 たとえば、C:\Fileact\ServerLocation です。|  
    |**PollingInterval**|適切な秒単位で確認間隔をアダプター ファイル転送の状態を入力します。|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG ヘルプを参照してください。|  
    |**[ユーザー名]**|SAG への接続に使用するユーザー名を入力します。|  
  
5.  クリックして**OK** FILEACT トランスポートのプロパティ ダイアログ ボックスを閉じます。  
  
6.  クリックして**OK** FILEACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。  
  
7.  メッセージ ボックスで、次のようにクリックします。 **OK**、し FileAct のホスト インスタンスを再起動します。  
  
## <a name="complete-steps"></a>手順を完了します
 [FileAct ストア アンド フォワード シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)   
 [手順 2:FileAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加します。](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md)   
 [ステップ 3:送信ポートを作成し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [手順 4:テスト FileAct ストア アンド フォワード エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)