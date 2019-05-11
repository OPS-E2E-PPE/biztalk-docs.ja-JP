---
title: 手順 1:InterAct ストア アンド フォワード (プル) シナリオ用に SWIFT アダプターを構成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4182021c-36c9-4c96-b2fa-e23c87862cfe
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a609ad94e6d8b0dcafb50d1025159b1dfcdde5af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366493"
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-pull-scenario"></a>手順 1:InterAct ストア アンド フォワード (プル) シナリオ用に SWIFT アダプターを構成します。
この手順を開始する前に行う必要があります[チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)します。  
  
### <a name="to-configure-the-swift-adapter"></a>SWIFT アダプターを構成するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk Server 管理コンソールを展開し、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**、右クリックして**INTERACT**、 をポイント**新規**、 をクリックし、**送信ハンドラー**します。  
  
3.  **アダプター ハンドラーのプロパティ-対話** ダイアログ ボックスで、**全般** タブから、**ホスト名**ドロップダウン リストで、 **interacthost**、 をクリックし、**プロパティ**します。  
  
4.  **トランスポートのプロパティの対話** ダイアログ ボックスで、**プロパティ** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**引数**|次の引数を入力: – SagMessagePartner \<SAG で対話するクライアントのメッセージのパートナーが作成された\>**に注意してください。** 引数のクライアントは、SAG で構成した MessagePartner です。|  
    |**暗号モード**|ドロップダウン リストから選択**詳細**します。|  
    |**LogMessageBody**|ドロップダウン リストから選択**FALSE**します。 **注:** TRUE に設定した場合は、BizTalk 追跡データベースでメッセージの本文を保持します。 ただし、セキュリティ上の理由から、メッセージ本文は、BAM ポータルでは表示ことはありませんすることができます。|  
    |**し**|ドロップダウン リストから選択**TRUE**します。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**[有効化]**|False です。|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG ヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
  
5.  クリックして**OK**対話トランスポートのプロパティのダイアログ ボックスを閉じます。  
  
6.  クリックして**OK** INTERACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。  
  
7.  メッセージ ボックスで、次のようにクリックします。 **OK**、し、対話のホスト インスタンスを再起動します。  
  
8.  手順 1. を繰り返します。  
  
9. コンソール ツリーで、BizTalk Server 管理コンソールを展開し、展開、 **BizTalk**グループで、[**プラットフォームの設定**、展開**アダプター**を開き、操作を選択 **[Biztalkserverapplication]** ] をクリックし、**プロパティ**します。  
  
10. **トランスポートのプロパティの対話** ダイアログ ボックスで、**プロパティ** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**引数**|次の引数を入力: – SagMessagePartner \<SAG で対話するクライアントのメッセージのパートナーが作成された\>**に注意してください。** 引数のクライアントは、SAG で構成した MessagePartner です。|  
    |**暗号モード**|ドロップダウン リストから選択**詳細**します。|  
    |**LogMessageBody**|ドロップダウン リストから選択**FALSE**します。 **注:** TRUE に設定した場合は、BizTalk 追跡データベースでメッセージの本文を保持します。 ただし、セキュリティ上の理由から、メッセージ本文は、BAM ポータルでは表示ことはありませんすることができます。|  
    |**し**|ドロップダウン リストから選択**TRUE**します。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**[有効化]**|True|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG ヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
  
11. クリックして**OK**対話トランスポートのプロパティのダイアログ ボックスを閉じます。  
  
12. 選択**既定のハンドラーをこのように**オプション。  
  
13. クリックして**OK** INTERACT-アダプター ハンドラーのプロパティのダイアログ ボックスを閉じます。  
  
14. メッセージ ボックスで、次のようにクリックします。 **OK**、し、再起動、 **BizTalkServerApplication**ホスト インスタンス。  
  
## <a name="see-also"></a>参照  
 [ステップ 2:送信ポートの作成し、InterAct ストア アンド フォワード (プル) シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-2-create-send-ports-and-receive-ports-for-the-interact-store-and-forward.md)   
 [手順 3:InterAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートとオーケストレーションを作成します。](../../adapters-and-accelerators/fileact-interact/step-3-create-orchestration-with-dynamic-send-for-interact-store-and-forward.md)   
 [手順 4:InterAct ストア アンド フォワード (プル) エンド ツー エンドのシナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-pull-end-to-end-scenario.md)