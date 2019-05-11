---
title: 手順 7:取引先に、受信確認を送信する送信ポートの構成 |Microsoft Docs
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
ms.openlocfilehash: a56aaa86e06ed7ebd728f1c5e4e49a6806105895
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244419"
---
# <a name="step-7-configure-a-send-port-to-send-the-acknowledgment-to-your-trading-partner"></a>手順 7:取引先に、受信確認を送信する送信ポートの構成します。
![手順 9 の 7](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")  

 この手順では、によって生成された 997 受信確認メッセージを送信する送信ポートを構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]fabrikam **toTHEM_997**フォルダー。  

## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  

### <a name="to-configure-a-send-port-that-subscribes-to-the-997-acknowledgment"></a>997 受信確認をサブスクライブする送信ポートを構成するには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。  

2. **送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  

   |プロパティ|目的|  
   |--------------|----------------|  
   |**名前**|入力`toTHEM_997`します。|  
   |**型**|選択**ファイル**します。|  
   |**構成**|をクリックして**構成**です。|  

   > [!NOTE]
   >  送信ポートのトランスポートの種類は、997 がフォルダーに配信されるフラット ファイルであるために、ファイルです。  

3. **FILE トランスポートのプロパティ** ダイアログ ボックスで、次の操作をクリックして**OK**:  


   |        プロパティ        |                                                                                                              目的                                                                                                              |
   |------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **コピー先フォルダー** | をクリックして**参照**、し、**フォルダーの参照** ダイアログ ボックスに移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi インターフェイス Developer tutorial \processedi_testlocations\ シナリオ a \tothem_997 します。 |
   |     **[ファイル名]**      |                                                                                           入力`%MessageID%.txt`、 をクリックし、 **OK**。                                                                                            |

   > [!NOTE]
   >  値を設定、**ファイル名**プロパティにより、出力ファイルは .txt 拡張子があるようになります。  

4. **送信ポートのプロパティ** ダイアログ ボックスの**送信パイプライン**を選択します**EdiSend**します。  

   > [!NOTE]
   >  AS2 トランスポートを経由して配信されるものを除く、EDI インターチェンジを送信するために使用する送信パイプラインは、EdiSend パイプラインです。 (AS2EdiSend 送信パイプラインは、AS2 トランスポート経由で配信される EDI インターチェンジの送信に使用されます)。  

5. コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。  


   |   プロパティ   |                           目的                           |
   |--------------|----------------------------------------------------------------|
   | **プロパティ** |                  選択**BTS します。MessageType**します。                   |
   | **[演算子]** |                         選択 **==** します。                         |
   |  **[値]**   | 入力 **<http://schemas.microsoft.com/Edi/X12#X12_997_Root>** します。 |

   > [!NOTE]
   >  フィルターにより、送信ポートは、997 メッセージの種類とメッセージをします。  

6. **[OK]** をクリックします。  

7. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**送信ポート**します。 右クリックして**toTHEM_997**、順にクリックします**開始**を参加させて、ポートを開始します。  

8. BizTalk Server 管理コンソールのコンソール ツリーでクリックして**プラットフォームの設定**、 をクリックし、**ホスト インスタンス**。 ホスト インスタンス ペインで次のようにクリックします。 **BizTalkServerApplication**、 をクリックし、**再起動**。  

## <a name="next-steps"></a>次の手順  
 2 つの取引先パートナー間のアグリーメントを作成する」の説明に従って[手順 8。パーティ間の取引先のパートナー アグリーメントを構成する](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)します。  

## <a name="see-also"></a>参照  
 [EDI インターチェンジと受信確認を送信するための静的送信ポートの構成](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)