---
title: '手順 8 C: HI システム用のパーティ情報を構成する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ac5c113-7ee7-4009-8ca3-d263f74c7a8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af1d853e381da6cbfbbe96fa805ca6396a1b7aae
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961072"
---
# <a name="step-8c-configure-party-information-for-the-hi-system"></a>手順 8 C: HI システム用のパーティ情報を構成します。
この手順では、HI システム用のパーティ情報を構成します。  
  
### <a name="to-configure-the-hi-system-party-information"></a>HI システム パーティ情報を構成するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。  
  
2.  パーティのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**Tutorial_HISystem**です。  
  
3.  コンソール ツリーでクリックして**送信ポート**です。  
  
4.  送信ポート] ペインで [空白のフィールドをクリックして、**名前**列で、選択**Tutorial_MllpSend**、クリックして **[ok]** です。  
  
5.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、クリックして**BTAHL7 構成エクスプ ローラー**です。  
  
6.  BTAHL7 構成エクスプ ローラーで、選択、 **MSH マップ**タブをクリックし、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**MSH3**|型**BTAHL7**、 **IE**、および**UUID**最初に、2 番目し、3 番目にメッセージ ボックスのそれぞれします。|  
    |**MSH5**|型**HI**、**システム**、および**GUID**最初に、2 番目し、3 番目にメッセージ ボックスのそれぞれします。|  
    |**MSH9**|型**ADT**と**A04**番目と 2 番目のメッセージ ボックスに、それぞれします。|  
    |**MSH12**|型**2.4**です。|  
    |**MSH15**|選択**SU**メッセージの転送が成功した後に受信確認を送信します。|  
    |**MSH16**|選択**NE**受信確認を送信しないようにします。|  
  
7.  をクリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。  
  
    > [!NOTE]
    >  構成情報がこのシナリオで必要ないため、BTAHL7 インターフェイス エンジンのシステムでは、パーティ情報を作成する必要はありません。  
  
 進みます[手順 9: BizTalk Server を再起動して](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)です。