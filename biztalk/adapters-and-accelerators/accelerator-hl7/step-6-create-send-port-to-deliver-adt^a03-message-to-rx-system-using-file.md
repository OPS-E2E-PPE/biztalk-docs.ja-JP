---
title: "手順 6: ADT を配信する送信ポートを作成する ^ A03 メッセージをファイル アダプターを使用して RX システム |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: 66c4b524-c8ff-43b5-9c44-6d7bc759ae2c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c25a348fb739f4558f1507eda0d46d209cd44c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a>手順 6: ADT を配信する送信ポートを作成する ^ A03 メッセージをファイル アダプターを使用して RX システム
この手順で、送信ポートの薬局システム (RX)、ファイル アダプターを使用してを作成します。  
  
### <a name="to-create-the-tutorialsendmsgrx-send-port"></a>Tutorial_sendMsg_RX 送信ポートを作成するには  
  
1.  [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]管理コンソールを右クリックして**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  **送信ポートのプロパティ** ダイアログ ボックスを次の操作を実行してクリックして**OK**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**Tutorial_sendMsg_RX**です。|  
    |**トランスポートの種類**|選択**ファイル**ドロップダウン リストからです。|  
    |**構成**|をクリックして**構成**を開くには、 **File トランスポートのプロパティ** ダイアログ ボックス。|  
  
3.  ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作を行うし、をクリックして**OK**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**コピー先フォルダー**|参照 **\<** *ドライブ***: > \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\End エンドツー エンド Tutorial\Tutorial_sendMsg_RX**.|  
    |**ファイル名**|型**%MessageID%.txt** (拡張子 .txt に .xml 拡張子を置き換えます)。|  
  
4.  **送信ポートのプロパティ**] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。  
  
5.  左のペインで選択**フィルター**、次の操作を実行します。 続行するには、 **[OK]** をクリックします。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**(1 行目)|選択**BTS です。MessageType**ドロップダウン リストからです。|  
    |**演算子**|選択**! =**ドロップダウン リストからです。|  
    |**値**|型**http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**です。|  
    |**グループ化**|選択**または**ドロップダウン リストからです。|  
    |**プロパティ**(2 番目の行)|下のフィールドをクリックして**プロパティ**、し、 **BTS です。MessageType**ドロップダウン リストからです。|  
    |**演算子**|選択**! =**ドロップダウン リストからです。|  
    |**値**|型**http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF です。**|  
    |**グループ化**|選択**AND**ドロップダウン リストからです。|  
    |**プロパティ**(3 行目)|選択**BTAHL7Schemas.MSH3_1**です。|  
    |**演算子**|選択 **==** ドロップダウン リストからです。|  
    |**値**|型**Tutorial_ADTSystem**です。|  
  
    > [!NOTE]
    >  最初のフィルターは、病院情報システム (HIS) は、メッセージの受信確認にないにサブスクライブしていることを意味します。 2 番目のフィルターでは、ソースは、受付放電と転送 (ADT) のシステム メッセージに、彼はサブスクライブしていることを意味します。  
  
    > [!NOTE]
    >  ファイルの格納場所にメッセージをドロップする BTAHL7 \<*ドライブ*>: プログラム FilesMicrosoft BizTalk <version> HL7SDKEnd エンドツー エンド TutorialTutorial_sendMsg_RX のアクセラレータです。  
  
6.  をクリックして**適用**、クリックして**[ok] です。**  
  
7.  管理コンソールで、をクリックして**送信ポート**を右クリックして**Tutorial_sendMsg_RX**、クリックして**開始**です。  
  
 進みます[手順 7: ADT を配信する送信ポートを作成 ^ MLLP アダプターを使用して自分に A03 メッセージ](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)です。