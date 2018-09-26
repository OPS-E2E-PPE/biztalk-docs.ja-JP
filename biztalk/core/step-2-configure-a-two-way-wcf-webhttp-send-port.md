---
title: '手順 2: 双方向 Wcf-webhttp 送信ポートの構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bcab296-7921-4df4-abcc-eea78cc827e8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f355275f9480cfa13f3a15bcc6522fbe7ec83b8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278890"
---
# <a name="step-2-configure-a-two-way-wcf-webhttp-send-port"></a>手順 2: 双方向 Wcf-webhttp 送信ポートを構成します。
この手順で構成する、双方向**Wcf-webhttp**米国航空会社のスケジュールで遅延を取得するための REST リソース URL を起動するポートを送信します。  
  
### <a name="to-configure-wcf-webhttp-send-port"></a>WCF-WebHttp 送信ポートを構成するには  
  
1.  BizTalk Server 管理コンソールから下にある、 **BizTalk アプリケーション 1**  ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリック**静的送信請求-応答送信ポート**です。  
  
2.  **[全般]** タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**SendPortRESTAzureMarketPlace**です。|  
    |**型**|選択**Wcf-webhttp**です。|  
    |**送信ハンドラー**|**[BizTalkServerApplication]** を選択します。|  
    |**送信パイプライン**|選択**PassThruTransmit**です。|  
    |**受信パイプライン**|選択**PassThruReceive**です。|  
  
     をクリックして**構成**です。  
  
3.  **Wcf-webhttp トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  **全般** タブの**アドレス (URI)**、入力`https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`です。  
  
    2.  [全般] タブの**HTTP メソッドと URL マッピング**次を入力します。  
  
        ```  
        <BtsHttpUrlMapping>  
        <Operation Method="GET" Url="/On_Time_Performance" />  
        </BtsHttpUrlMapping>  
  
        ```  
  
         ここでは、**取得**HTTP 動詞および**On_Time_Performance**はフライトの遅延を取得するための一意のリソース URL を構築するためにベース URI に追加されます。  
         
         > [!TIP] 
         > [URL] フィールド内で任意の特殊な XML 文字エスケープする必要が""です。 これにより、XML の特殊文字は、処理、ポートでは保持されます。 たとえば、`&`として特殊文字をエスケープする必要があります`&amp;`です。 
           >
           >差出人：`Url=”/Customer?{ID}& group=Location”`
           >
           >
           >宛先：`Url=”/Customer?{ID}&amp;group=Location”`
  
    3.  **バインド** タブの**最大受信メッセージ サイズ**フィールドに、十分な大きさの値を選択します。 通常、フライトの状況が含まれている応答メッセージはサイズがかなり大きく、指定された既定のメッセージ サイズを超える可能性があるためです。  
  
    4.  **セキュリティ** タブで、次の操作します。  
  
        1.  **セキュリティ モード****トランスポート**です。  
  
        2.  **クライアント資格情報の種類のトランスポート****基本**です。  
  
        3.  下にある、**ユーザー名資格情報**ボックスで、クリックして**編集**です。 **クライアントの資格情報**ダイアログ ボックスで、**シングル サインオンに使用しない**、ユーザー名とから取得したパスワードを入力し、**マイ アカウント**した後タブログインして[Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913)です。 に対して資格情報が表示されている、**顧客 ID** (ユーザー名) と**プライマリ アカウント キー** (パスワード) ラベル。  
  
        4.  **[OK]** をクリックします。  
  
    5.  **メッセージ** タブの**動詞の本文を抑制**、要求メッセージからメッセージ ペイロードを除去する動詞を指定します。 このチュートリアルを指定`GET`です。 その理由を次に示します: 米国航空会社のフライト遅延の REST エンドポイントに対する GET メソッド呼び出しには、メッセージ ペイロードは不要REST リソース URL は、情報を取得するだけで十分です。 ただし、トリガーを**Wcf-webhttp** rest 呼び出しを送信ポート、いくつかのメッセージ本文を持つダミー メッセージをドロップします。 前に説明したように、REST エンドポイントはメッセージのペイロードを想定していないので、送信ポートから REST エンドポイントにダミー メッセージを送信できません。 そのため、REST エンドポイントを呼び出す前に、アダプターを切り離しますで指定した動詞についてのみ、ダミー メッセージからメッセージ ペイロード、**動詞の本文を抑制**テキスト ボックス。  
  
    6.  をクリックして**OK**送信ポートのプロパティ ダイアログ ボックスに戻るまでです。 左側のウィンドウからをクリックして**フィルター**で作成したポートの受信側から受信したすべてのメッセージを処理するフィルターを指定して[手順 1: ファイルの受信場所を構成する](../core/step-1-configure-a-file-receive-location.md)です。  
  
        |||  
        |-|-|  
        |**プロパティ**|設定**BTS です。ReceivePortName**|  
        |**演算子**|を設定します。**==**|  
        |**値**|を設定します。`ReceivePortRestAzureMarketPlace`|  
  
    7.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 5: BizTalk Server を使用して REST インターフェイスの呼び出し](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)