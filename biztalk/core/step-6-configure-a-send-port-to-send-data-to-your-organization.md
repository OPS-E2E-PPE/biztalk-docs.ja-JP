---
title: '手順 6: データを組織に送信する送信ポートの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 796570ca-8178-4679-9213-d67a2a189bf9
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b38182ff9f46688447e11f444ab543d8e0aa1d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975179"
---
# <a name="step-6-configure-a-send-port-to-send-data-to-your-organization"></a>手順 6: データを組織に送信する送信ポートを構成します。
![手順 9 の 6](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")  

 このステップでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から組織を表す OrderSystem パーティに 850 メッセージを送信するように送信ポートを構成します。 この送信ポートに適用されます、 **Inbound4010850_to_OrderFile**入力メッセージの形式からマップで指定された形式への出力メッセージを変換するマップ。  

## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  

### <a name="to-configure-a-send-port-for-the-850-message"></a>850 メッセージの送信ポートを構成するには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリック**パイプライン**、 をクリックし、**更新**。  

   > [!NOTE]
   >  作成する送信ポートに SendOrderFilePipeline を選択できるようにするには、パイプラインの一覧の更新が必要な場合があります。  

2. 右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**します。  

3. **送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  

   |プロパティ|目的|  
   |--------------|----------------|  
   |**名前**|入力`toOrderSystem`します。|  
   |**型**|選択**ファイル**します。|  
   |**構成**|クリックして**構成**します。|  

   > [!NOTE]
   >  テスト メッセージはフォルダに配信されるフラット ファイルであるため、送信ポートのトランスポートの種類は FILE です。  

4. **FILE トランスポートのプロパティ** ダイアログ ボックスで、次の操作をクリックして**OK**:  


   |        プロパティ        |                                                                                                               目的                                                                                                               |
   |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **コピー先フォルダー** | クリックして**参照**、し、**フォルダーの参照** ダイアログ ボックスに移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\ シナリオ a \toordersystem |
   |     **[ファイル名]**      |                                                                                            入力`%MessageID%.txt`、 をクリックし、 **OK**。                                                                                             |

   > [!NOTE]
   >  値を設定、**ファイル名**プロパティにより、出力ファイルは .txt 拡張子があるようになります。  

5. **送信ポートのプロパティ** ダイアログ ボックスの**送信パイプライン**を選択します**SendOrderFilePipeline**します。  

   > [!NOTE]
   >  **SendOrderFilePipeline**送信パイプラインには、入力 850 メッセージからマップされたデータを使用して .txt 出力ファイルを作成フラット ファイル アセンブラーが含まれています。 出力ファイルは .txt ファイルのため、インターチェンジ/確認の状態レポートには表示されません。  

6. コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。  

   |プロパティ|目的|  
   |--------------|----------------|  
   |**プロパティ**|選択**BTS します。ReceivePortName**します。|  
   |**[演算子]**|選択 **==** します。|  
   |**[値]**|入力`ReceiveEDI_fromTHEM_A`します。|  
   |**グループ化**|選択**と**します。|  
   |**プロパティ**|次の行に次のように選択します。 **BTS します。MessageType**します。|  
   |**[演算子]**|選択 **! =** します。|  
   |**[値]**|入力`http://schemas.microsoft.com/Edi/X12#X12_997_Root`します。|  

   > [!NOTE]
   >  フィルターにより、送信ポートは Receive_EDI_fromTHEM_A 受信場所で受信されたメッセージを取得し、997 受信確認ではなく 850 メッセージのみを取得します。  

7. コンソール ツリーで、クリックして **[outboundmaps]** します。 **送信マップ** ウィンドウで、**マップ**列の選択の最初の行で**Inbound4010850_to_OrderFile**します。 (エントリ、**ソース ドキュメント**列は X12_00401_850 になります)。  

   > [!NOTE]
   >  この手順により、出力メッセージはに従って入力メッセージからマップされたデータののみで構成されること、 **Inbound4010850_to_OrderFile**マップします。  

8. **[OK]** をクリックします。  

9. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**送信ポート**します。 右クリックして**toOrderSystem**、順にクリックします**開始**を参加させて、ポートを開始します。  

## <a name="next-steps"></a>次の手順  
 送信ポートを構成する (**toTHEM_997**) を 997 受信確認を Fabrikam に返信」の説明に従って[手順 7:、取引先パートナーに、受信確認を送信する送信ポート構成](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)します。  

## <a name="see-also"></a>参照  
 [EDI インターチェンジと受信確認を送信するための静的送信ポートの構成](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)