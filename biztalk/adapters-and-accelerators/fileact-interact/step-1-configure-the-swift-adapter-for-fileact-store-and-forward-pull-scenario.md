---
title: 手順 1:FileAct ストア アンド フォワード プル シナリオ用に SWIFT アダプターを構成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc271544-6bc8-4d62-aba0-3fe3295f2a2a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b3f5d4c6698f06a49b0a5ba2bf6a862a9592a3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366538"
---
# <a name="step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario"></a>手順 1:FileAct ストア アンド フォワード プル シナリオ用に SWIFT アダプターを構成します。
完全な[チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)この手順を開始する前にします。
  
## <a name="configure-the-swift-adapter"></a>SWIFT アダプターを構成します。  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**、右クリックして**FILEACT**、 をポイント**新規**、 をクリックし、**送信ハンドラー**します。  
  
3.  **FILEACT – アダプター HandlerProperties**  ダイアログ ボックスの 、**全般** タブから、**ホスト名**ドロップダウン リストで、 **FileActHost**、 をクリックし、**プロパティ**します。  
  
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
    |**PollingInterval**|Pollinginterval プロパティには、適切な値を入力します。 たとえば、5 です。 これは、秒単位で確認間隔をアダプター ファイル転送の状態を示します。|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG ヘルプを参照してください。|  
    |**[ユーザー名]**|SAG への接続に使用するユーザー名を入力します。|  
  
5.  クリックして**OK** FILEACT トランスポートのプロパティ ダイアログ ボックスを閉じます。  
  
6.  クリックして**OK** FILEACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。  
  
7.  メッセージ ボックスで、次のようにクリックします。 **OK**、し FileAct のホスト インスタンスを再起動します。  
  
8.  手順 1. を繰り返します。  
  
9. コンソール ツリーで、展開**BizTalk Server 管理**、展開、 **BizTalk**グループで、[**プラットフォームの設定**、展開**アダプター**を選択します**FILEACT**オープン**BizTalkServerApplication** ] をクリックし、**プロパティ**。  
  
10. **FILEACT トランスポートのプロパティ** ダイアログ ボックスの 、**プロパティ** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**引数**|次の引数を入力: – SagMessagePartner \<SAG で Fileact クライアント メッセージのパートナーが作成される\>**に注意してください。** 引数のクライアントは、SAG で構成した MessagePartner です。|  
    |**暗号モード**|ドロップダウン リストから選択**詳細**します。|  
    |**LogMessageBody**|ドロップダウン リストから選択**TRUE**します。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。 **注:** TRUE に設定した場合は、BizTalk 追跡データベースでメッセージの本文を保持します。 ただし、セキュリティ上の理由から、メッセージ本文は、BAM ポータルでは表示ことはありませんすることができます。|  
    |**し**|ドロップダウン リストから選択**TRUE**します。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**[有効化]**|**True**|  
    |**イベントのエンドポイント**|適切な SAG エンドポイントを入力します。|  
    |**PhysicalFolderName**|サーバー上のフォルダーの名前を入力します。 たとえば、C:\Fileact\ServerLocation です。|  
    |**PollingInterval**|Pollinginterval プロパティには、適切な値を入力します。 たとえば、5 です。 これは、秒単位で確認間隔をアダプター ファイル転送の状態を示します。|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG ヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
  
11. FILEACT トランスポートのプロパティ ダイアログ ボックスを閉じるには、ok をクリックします。  
  
12. 選択はこの既定のハンドラーのオプションを設定します。  
  
13. FILEACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じるには、ok をクリックします。  
  
14. メッセージ ボックスで、[ok] をクリックし、BizTalkServerApplication ホスト インスタンスを再起動しています。  
  
## <a name="see-also"></a>参照  
 [手順 2:送信ポートを作成して、受信ポートを FileAct ストア アンド フォワード (プル) シナリオ](../../adapters-and-accelerators/fileact-interact/step-2-create-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [ステップ 3:作成および Fileact ストア アンド フォワード (プル) シナリオ用の動的送信ポートを使用したオーケストレーションのバインド](../../adapters-and-accelerators/fileact-interact/step-3-create-and-bind-an-orchestration-with-dynamic-send-port-for-file-act.md)   
 [手順 4:テスト FileAct ストア アンド フォワード (プル) エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-pull-end-to-end-scenario.md)