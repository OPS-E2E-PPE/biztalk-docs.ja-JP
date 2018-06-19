---
title: '手順 7: 取引先に、受信確認を送信する送信ポートの構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a082870-894c-4f64-a575-3681d8a5c4ea
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59d36aaaf33673095c664363da5b3417bbd1cde4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279066"
---
# <a name="step-7-configure-a-send-port-to-send-the-acknowledgment-to-your-trading-partner"></a>手順 7: 取引先に、受信確認を送信する送信ポートを構成します。
![手順 9 の 7](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")  
  
 によって生成された 997 受信確認メッセージを送信する送信ポートを構成するこの手順で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]fabrikam **toTHEM_997**フォルダーです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-a-send-port-that-subscribes-to-the-997-acknowledgment"></a>997 受信確認をサブスクライブするように送信ポートを構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|入力`toTHEM_997`です。|  
    |**型**|選択**ファイル**です。|  
    |**構成**|をクリックして**構成**です。|  
  
    > [!NOTE]
    >  997 はフォルダに配信されるフラット ファイルなので、送信ポートのトランスポートの種類は FILE です。  
  
3.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、次の操作をクリックして**OK**:  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**コピー先フォルダー**|をクリックして**参照**、し、[、**フォルダーの参照**] ダイアログ ボックスに移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi インターフェイス Developer tutorial \processedi_testlocations\ シナリオ a \tothem_997 です。|  
    |**ファイル名**|入力`%MessageID%.txt`、順にクリック**OK**です。|  
  
    > [!NOTE]
    >  値を設定、**ファイル名**プロパティ出力ファイルが .txt 拡張子を持つことを確認します。  
  
4.  **送信ポートのプロパティ**] ダイアログ ボックスの**送信パイプライン**[ **EdiSend**です。  
  
    > [!NOTE]
    >  AS2 トランスポートを経由して配信されるインターチェンジ以外の EDI インターチェンジの送信に使用される送信パイプラインは、EdiSend パイプラインです (AS2 トランスポートを経由して配信される EDI インターチェンジの送信に使用される送信パイプラインは、AS2EdiSend 送信パイプラインです)。  
  
5.  コンソール ツリーでクリックして**フィルター**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**BTS です。MessageType**です。|  
    |**演算子**|選択 **==** です。|  
    |**値**|入力**http://schemas.microsoft.com/Edi/X12#X12_997_Root**です。|  
  
    > [!NOTE]
    >  このフィルターにより、送信ポートは種類が 997 のメッセージを抽出します。  
  
6.  **[OK]** をクリックします。  
  
7.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**送信ポート**です。 右クリック**toTHEM_997**、クリックして**開始**を参加させて、ポートを開始します。  
  
8.  BizTalk Server 管理コンソールで、コンソール ツリーで、をクリックして**プラットフォームの設定**、クリックして**ホスト インスタンス**です。 ホスト インスタンス ペインでをクリックして**BizTalkServerApplication**、クリックして**再起動**です。  
  
## <a name="next-steps"></a>次の手順  
 」の説明に従って、2 つの取引パートナー間のアグリーメントを作成する[手順 8: 当事者間の取引先アグリーメントを構成する](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)です。  
  
## <a name="see-also"></a>参照  
 [EDI インターチェンジと確認を送信する静的な送信ポートを構成します。](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)