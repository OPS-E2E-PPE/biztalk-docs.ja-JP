---
title: "手順 1: InterAct ストア アンド フォワード (プル) シナリオの迅速な対応アダプターを構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4182021c-36c9-4c96-b2fa-e23c87862cfe
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 831a311a23e6d24f1a655d0df604032a02cb782d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-pull-scenario"></a>手順 1: InterAct ストア アンド フォワード (プル) シナリオの迅速な対応アダプターを構成します。
この手順を開始する前に行う必要があります[、チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)です。  
  
### <a name="to-configure-the-swift-adapter"></a>SWIFT のアダプターを構成するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk Server 管理コンソールを展開し、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**を右クリックして**INTERACT**、 をポイント**新規**、クリックして**送信ハンドラー**です。  
  
3.  **アダプター ハンドラーのプロパティ-[対話**ダイアログ ボックスの**全般**] タブから、**ホスト名**ドロップダウン リストで、 **interacthost**、クリックして**プロパティ**です。  
  
4.  **トランスポートのプロパティの対話** ダイアログ ボックスで、**プロパティ** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**引数**|次の引数を入力: – SagMessagePartner \<SAG で対話するクライアントのメッセージのパートナーが作成された >**注:**引数で、クライアントは SAG で構成されている MessagePartner です。|  
    |**暗号化モード**|ドロップダウン リストから選択**詳細**です。|  
    |**LogMessageBody**|ドロップダウン リストから選択**FALSE**です。 **注:**を TRUE に設定する場合、BizTalk 追跡データベースでメッセージ本文が保持されます。 ただし、セキュリティ上の理由から、メッセージの本文見なすことができることはありません、BAM ポータルにします。|  
    |**し**|ドロップダウン リストから選択**TRUE**です。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**[有効化]**|False : |  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG のヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
  
5.  をクリックして**OK**対話トランスポートのプロパティ ダイアログ ボックスを閉じます。  
  
6.  をクリックして**OK** INTERACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。  
  
7.  メッセージ ボックスで、をクリックして**OK**、し対話するホスト インスタンスを再起動します。  
  
8.  手順 1. を繰り返します。  
  
9. コンソール ツリーで、BizTalk Server 管理コンソールを展開し、 **BizTalk**グループで、[**プラットフォームの設定**、展開**アダプター**対話を選択し、を開く**BizTalkServerApplication** ] をクリックし、**プロパティ**です。  
  
10. **トランスポートのプロパティの対話** ダイアログ ボックスで、**プロパティ** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**引数**|次の引数を入力: – SagMessagePartner \<SAG で対話するクライアントのメッセージのパートナーが作成された >**注:**引数で、クライアントは SAG で構成されている MessagePartner です。|  
    |**暗号化モード**|ドロップダウン リストから選択**詳細**です。|  
    |**LogMessageBody**|ドロップダウン リストから選択**FALSE**です。 **注:**を TRUE に設定する場合、BizTalk 追跡データベースでメッセージ本文が保持されます。 ただし、セキュリティ上の理由から、メッセージの本文見なすことができることはありません、BAM ポータルにします。|  
    |**し**|ドロップダウン リストから選択**TRUE**です。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**[有効化]**|True|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG のヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
  
11. をクリックして**OK**対話トランスポートのプロパティ ダイアログ ボックスを閉じます。  
  
12. 選択**しやすいように、既定のハンドラー**オプション。  
  
13. をクリックして**OK** INTERACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。  
  
14. メッセージ ボックスで、をクリックして**OK**、し、再起動、 **BizTalkServerApplication**ホスト インスタンス。  
  
## <a name="see-also"></a>参照  
 [ステップ 2: 送信ポートを作成し、対話ストア アンド フォワード (プル) シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-2-create-send-ports-and-receive-ports-for-the-interact-store-and-forward.md)   
 [手順 3: InterAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートにオーケストレーションを作成します。](../../adapters-and-accelerators/fileact-interact/step-3-create-orchestration-with-dynamic-send-for-interact-store-and-forward.md)   
 [手順 4: InterAct ストア アンド フォワード (プル) エンド ツー エンドのシナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-pull-end-to-end-scenario.md)