---
title: "手順 8B: RX システム用のパーティ情報を構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0b34ec9-220d-4a6b-9712-54c8099b663b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29ab7194e0e1b81a773c61123de9171f1c65eb0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-8b-configure-party-information-for-the-rx-system"></a>手順 8B: RX システム用のパーティ情報を構成します。
この手順では、RX システム用のパーティ情報を構成します。  
  
### <a name="to-configure-the-rx-system-party-information"></a>RX システム パーティ情報を構成するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。  
  
2.  パーティのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**Tutorial_RXSystem**です。  
  
3.  コンソール ツリーでクリックして**送信ポート**です。  
  
4.  送信ポート] ペインで [空白のフィールドをクリックして、**名前**列で、選択**Tutorial_sendMsg_RX**、クリックして**[ok]**です。  
  
5.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン > Accelerator 用 HL7**、クリックして**BTAHL7構成のエクスプ ローラー**です。  
  
6.  BTAHL7 構成エクスプ ローラーで、選択、 **MSH マップ**タブをクリックし、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**MSH3**|型**BTAHL7**左のテキスト ボックスにします。|  
    |**MSH5**|型**Tutorial_RXSystem**左のテキスト ボックスにします。|  
  
7.  をクリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。  
  
 進みます[手順 8 C: HI システム用のパーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md)です。