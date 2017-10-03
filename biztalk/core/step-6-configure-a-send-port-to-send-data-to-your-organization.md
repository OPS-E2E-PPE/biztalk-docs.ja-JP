---
title: "手順 6: 組織にデータを送信する送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 796570ca-8178-4679-9213-d67a2a189bf9
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b513725024aec755515ccac998745220ee5dfa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-configure-a-send-port-to-send-data-to-your-organization"></a>手順 6: 組織にデータを送信する送信ポートを構成します。
![手順 9 の 6](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")  
  
 このステップでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から組織を表す OrderSystem パーティに 850 メッセージを送信するように送信ポートを構成します。 この送信ポートが適用されます、 **Inbound4010850_to_OrderFile**出力メッセージを入力メッセージの形式からマップで指定された形式を変換するマップです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-a-send-port-for-the-850-message"></a>850 メッセージの送信ポートを構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**パイプライン**、クリックして**更新**です。  
  
    > [!NOTE]
    >  作成する送信ポートに SendOrderFilePipeline を選択できるようにするには、パイプラインの一覧の更新が必要な場合があります。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|入力`toOrderSystem`です。|  
    |**型**|選択**ファイル**です。|  
    |**構成**|をクリックして**構成**です。|  
  
    > [!NOTE]
    >  テスト メッセージはフォルダに配信されるフラット ファイルであるため、送信ポートのトランスポートの種類は FILE です。  
  
4.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、次の操作をクリックして**OK**:  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**コピー先フォルダー**|をクリックして**参照**、し、[、**フォルダーの参照**] ダイアログ ボックスに移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi インターフェイス Developer tutorial \processedi_testlocations\ シナリオ a \toordersystem|  
    |**ファイル名**|入力`%MessageID%.txt`、順にクリック**OK**です。|  
  
    > [!NOTE]
    >  値を設定、**ファイル名**プロパティ出力ファイルが .txt 拡張子を持つことを確認します。  
  
5.  **送信ポートのプロパティ**] ダイアログ ボックスの**送信パイプライン**[ **SendOrderFilePipeline**です。  
  
    > [!NOTE]
    >  **SendOrderFilePipeline**送信パイプラインには、入力 850 メッセージからマップされたデータを使用して .txt 出力ファイルをアセンブル フラット ファイル アセンブラーが含まれています。 出力ファイルは .txt ファイルのため、インターチェンジ/確認の状態レポートには表示されません。  
  
6.  コンソール ツリーでクリックして**フィルター**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**BTS です。ReceivePortName**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|入力`ReceiveEDI_fromTHEM_A`です。|  
    |**グループ化**|選択**と**です。|  
    |**プロパティ**|次の行では、次のように選択します。 **BTS です。MessageType**です。|  
    |**演算子**|選択**! =**です。|  
    |**値**|入力`http://schemas.microsoft.com/Edi/X12#X12_997_Root`です。|  
  
    > [!NOTE]
    >  フィルターにより、送信ポートは Receive_EDI_fromTHEM_A 受信場所で受信されたメッセージを取得し、997 受信確認ではなく 850 メッセージのみを取得します。  
  
7.  コンソール ツリーでクリックして**[outboundmaps]**です。 **送信マップ** ウィンドウで、**マップ**select の最初の行で、列**Inbound4010850_to_OrderFile**です。 (内のエントリ、**ソース ドキュメント**列は X12_00401_850 になります)。  
  
    > [!NOTE]
    >  この手順により、出力メッセージはに従って入力メッセージからマップされたデータののみで構成されること、 **Inbound4010850_to_OrderFile**マップします。  
  
8.  **[OK]**をクリックします。  
  
9. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**送信ポート**です。 右クリック**toOrderSystem**、クリックして**開始**を参加させて、ポートを開始します。  
  
## <a name="next-steps"></a>次の手順  
 送信ポートを構成する (**toTHEM_997**) 送信 997 受信確認を Fabrikam に返信」の説明に従って[手順 7:、取引先に、受信確認を送信する送信ポートを構成する](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)です。  
  
## <a name="see-also"></a>参照  
 [EDI インターチェンジと確認を送信する静的な送信ポートを構成します。](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)