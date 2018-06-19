---
title: '手順 1: FileAct ストア アンド フォワードのシナリオ用のアダプターを SWIFT の構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 3e2883bb75667d2ad2518a4b8bf0c2a90be79ec8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964280"
---
# <a name="step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario"></a>手順 1: FileAct ストア アンド フォワードのシナリオ用 SWIFT アダプターを構成します。
完全な[、チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)この手順を開始する前にします。
  
## <a name="configure-the-swift-adapter"></a>SWIFT のアダプターを構成します。  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**を右クリックして**FILEACT**、指す**新規**、順にクリック**送信ハンドラー**です。  
  
3.  **FILEACT – アダプター HandlerProperties**ダイアログ ボックスの**全般** タブから、**ホスト名**ドロップダウン リストで、 **fileacthost**、クリックして**プロパティ**です。  
  
4.  **FILEACT トランスポートのプロパティ** ダイアログ ボックスで、**プロパティ** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**引数**|次の引数を入力: - SagMessagePartner \<SAG で Fileact クライアント メッセージのパートナーが作成される\>**注:** 引数で、クライアントは SAG で構成されている MessagePartner です。|  
    |**暗号化モード**|ドロップダウン リストから選択**詳細**です。|  
    |**FACryptoMode**|ドロップダウン リストから選択**詳細**です。|  
    |**し**|ドロップダウン リストから選択**TRUE**です。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**[有効化]**|False|  
    |**イベントのエンドポイント**|適切な SAG エンドポイントを入力します。|  
    |**PhysicalFolderName**|サーバー上のフォルダーの名前を入力します。 たとえば、C:\Fileact\ServerLocation です。|  
    |**PollingInterval**|適切な間隔 (秒) アダプターを確認するまでのファイル転送の状態を入力します。|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG のヘルプを参照してください。|  
    |**[ユーザー名]**|SAG への接続に使用するユーザー名を入力します。|  
  
5.  をクリックして**OK** FILEACT トランスポートのプロパティ ダイアログ ボックスを閉じます。  
  
6.  をクリックして**OK** FILEACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。  
  
7.  メッセージ ボックスで、をクリックして**OK**、FileAct ホスト インスタンスを再起動します。  
  
## <a name="complete-steps"></a>詳細な手順
 [FileAct ストア アンド フォワードのシナリオ](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)   
 [手順 2: FileAct ストア アンド フォワードのシナリオの Paramfile に SWIFTNet 構成を追加します。](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md)   
 [手順 3: 送信ポートを作成し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [手順 4: FileAct ストア アンド フォワード エンド ツー エンド シナリオをテストする](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)