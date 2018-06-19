---
title: '手順 1: FileAct ストア アンド フォワード プル シナリオ用 SWIFT アダプターの構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 41e57df0f77718e3e36b5d0d68896def6a768be7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965200"
---
# <a name="step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario"></a>手順 1: FileAct ストア アンド フォワード プル シナリオ用 SWIFT アダプターを構成します。
完全な[、チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)この手順を開始する前にします。
  
## <a name="configure-the-swift-adapter"></a>SWIFT のアダプターを構成します。  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**を右クリックして**FILEACT**、指す**新規**、順にクリック**送信ハンドラー**です。  
  
3.  **FILEACT – アダプター HandlerProperties**ダイアログ ボックスの**全般** タブから、**ホスト名**ドロップダウン リストで、 **FileActHost**、クリックして**プロパティ**です。  
  
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
    |**PollingInterval**|Pollinginterval プロパティに適切な値を入力します。 たとえば、5 です。 これは、間隔 (秒) アダプターを確認するまでのファイル転送の状態を示します。|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG のヘルプを参照してください。|  
    |**[ユーザー名]**|SAG への接続に使用するユーザー名を入力します。|  
  
5.  をクリックして**OK** FILEACT トランスポートのプロパティ ダイアログ ボックスを閉じます。  
  
6.  をクリックして**OK** FILEACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。  
  
7.  メッセージ ボックスで、をクリックして**OK**、FileAct ホスト インスタンスを再起動します。  
  
8.  手順 1. を繰り返します。  
  
9. コンソール ツリーで  **BizTalk Server 管理コンソール**、展開、 **BizTalk**グループで、**プラットフォームの設定**、展開**アダプター** **FILEACT**、開かれている**BizTalkServerApplication**  をクリックし、**プロパティ**です。  
  
10. **FILEACT トランスポートのプロパティ** ダイアログ ボックスで、**プロパティ** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**引数**|次の引数を入力: – SagMessagePartner \<SAG で Fileact クライアント メッセージのパートナーが作成される\>**注:** 引数で、クライアントは SAG で構成されている MessagePartner です。|  
    |**暗号化モード**|ドロップダウン リストから選択**詳細**です。|  
    |**LogMessageBody**|ドロップダウン リストから選択**TRUE**です。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。 **注:** を TRUE に設定する場合、BizTalk 追跡データベースでメッセージ本文が保持されます。 ただし、セキュリティ上の理由から、メッセージの本文見なすことができることはありません、BAM ポータルにします。|  
    |**し**|ドロップダウン リストから選択**TRUE**です。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**[有効化]**|**True**|  
    |**イベントのエンドポイント**|適切な SAG エンドポイントを入力します。|  
    |**PhysicalFolderName**|サーバー上のフォルダーの名前を入力します。 たとえば、C:\Fileact\ServerLocation です。|  
    |**PollingInterval**|Pollinginterval プロパティに適切な値を入力します。 たとえば、5 です。 これは、間隔 (秒) アダプターを確認するまでのファイル転送の状態を示します。|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG のヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
  
11. FILEACT トランスポートのプロパティ ダイアログ ボックスを閉じるには、ok をクリックします。  
  
12. 選択はこの既定のハンドラー オプションを設定します。  
  
13. FILEACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じるには、ok をクリックします。  
  
14. メッセージ ボックスで、[ok] をクリックし、BizTalkServerApplication ホスト インスタンスを再起動します。  
  
## <a name="see-also"></a>参照  
 [手順 2: 送信ポートを作成し、FileAct ストア アンド フォワード (プル) シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-2-create-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [手順 3: を作成し、ファイル Act ストア アンド フォワード (プル) シナリオ用の動的送信ポートにオーケストレーションをバインド](../../adapters-and-accelerators/fileact-interact/step-3-create-and-bind-an-orchestration-with-dynamic-send-port-for-file-act.md)   
 [手順 4: FileAct ストア アンド フォワード (プル) エンド ツー エンド シナリオをテストする](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-pull-end-to-end-scenario.md)