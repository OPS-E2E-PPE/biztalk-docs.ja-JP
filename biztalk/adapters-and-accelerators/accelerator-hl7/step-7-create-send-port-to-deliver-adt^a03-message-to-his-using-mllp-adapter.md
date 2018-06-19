---
title: '手順 7: ADT を配信する送信ポートを作成する ^ MLLP アダプターを使用して自分に A03 メッセージ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: d9e7f281-3d25-4675-a13e-0e2057f5e69a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc122ab37ee0d618c3bd75792a5b88571dd49162
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206754"
---
# <a name="step-7-create-a-send-port-to-deliver-the-adta03-message-to-his-using-the-mllp-adapter"></a>手順 7: ADT を配信する送信ポートを作成する ^ MLLP アダプターを使用して自分に A03 メッセージ
この手順では、メッセージを送信する、病院情報システム (HIS) MLLP アダプターを使用して、送信ポートを作成します。  
  
### <a name="to-create-the-tutorialmllpsend-send-port"></a>Tutorial_MllpSend 送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  送信ポートのプロパティ ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**Tutorial_MllpSend**です。|  
    |**トランスポートの種類**|選択**MLLP**ドロップダウン リストからです。|  
    |**構成**|をクリックして**構成**を開くには、 **MLLP トランスポートのプロパティ** ダイアログ ボックス。|  
  
3.  MLLP トランスポートのプロパティ ダイアログ ボックスで、次の操作を行うし、をクリックして**OK**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**接続名**|型**1WaySend**です。|  
    |**ホスト**|型**localhost**です。|  
    |**[ポート]**|型**14000**です。|  
  
4.  送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。  
  
5.  左のペインで選択**フィルター**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**BTS です。ReceivePortName**ドロップダウン リストからです。|  
    |**演算子**|選択 **==** ドロップダウン リストからです。|  
    |**値**|型**Tutorial_1WayReceive**です。|  
  
    > [!NOTE]
    >  ポートのメッセージ 1WayReceive で指定されたポートをリッスンします。  
  
6.  をクリックして**適用**、クリックして **[ok] です。**  
  
7.  管理コンソールで、をクリックして**送信ポート**を右クリックして**Tutorial_MllpSend**、クリックして**開始**です。  
  
 進みます[手順 8: パーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)です。