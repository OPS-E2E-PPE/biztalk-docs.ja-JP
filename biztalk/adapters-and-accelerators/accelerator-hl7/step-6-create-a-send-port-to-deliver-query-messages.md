---
title: '手順 6: クエリ メッセージを配信する送信ポートの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: a3cfa2aa-888d-4a82-9eb3-2e9cc29ee582
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c373940d8ab1e847b66527d83ef24e952d84d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206802"
---
# <a name="step-6-create-a-send-port-to-deliver-query-messages"></a>手順 6: クエリ メッセージを配信する送信ポートを作成します。
この手順では、着信クエリを配信する送信ポートを作成 (クエリ ^ Q01 メッセージ) 病院情報システム (HIS) にします。  
  
### <a name="to-create-the-hissend-send-port"></a>HIS_Send 送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、指す**新規**、し、**静的な一方向送信ポート**です。  
  
2.  [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**HIS_Send**です。|  
    |**トランスポートの種類**|選択**MLLP**です。|  
    |**構成**|クリックして、**構成**の右側にあるボタン**型**です。|  
  
3.  MLLP トランスポートのプロパティ ダイアログ ボックスで、次の情報を入力し、クリックして**OK**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**接続名**|型**HIS_SendMLLP**です。|  
    |**ホスト**|型**localhost**です。|  
    |**[ポート]**|型**24000**です。|  
  
4.  送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。  
  
5.  コンソール ツリーでクリックして**フィルター**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|**プロパティ** **BTS です。MessageType**です。|  
    |**演算子**|選択 **==** ドロップダウン リストからです。|  
    |**値**|型**http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF**です。|  
    |**グループ化**|選択**AND**ドロップダウン リストからです。|  
    |**プロパティ**|**プロパティ**2 行目に次のように選択します。 **BTAHL7Schemas.MSH5_1**です。|  
    |**演算子**|選択 **==** ドロップダウン リストからです。|  
    |**値**|型**HIS**です。|  
  
    > [!NOTE]
    >  最初のフィルターは、送信ポートにのみ、クエリに準拠するメッセージが選択することを示す ^ 手順 3 a. で作成した Q01 スキーマです。 2 番目のフィルターを指定する変換先、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンは、これらのメッセージを送信します。  
  
6.  **[OK]** をクリックします。  
  
7.  管理コンソールで、次のように選択します。**送信ポート**、を右クリック**HIS_Send**、クリックして**開始**です。  
  
 進みます[手順 7: 応答メッセージを配信する送信ポートを作成](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)です。