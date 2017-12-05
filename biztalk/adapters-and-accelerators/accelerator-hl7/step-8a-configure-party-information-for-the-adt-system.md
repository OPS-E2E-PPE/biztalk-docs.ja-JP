---
title: "手順 8 a.: ADT システム用のパーティ情報を構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0d750c2-a3c6-4571-a4e1-0d0aaaa4d400
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42b92e3b55cd4de181103e28526abf3ecde29412
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-8a-configure-party-information-for-the-adt-system"></a>手順 8 a.: ADT システム用のパーティ情報を構成します。
この手順では、ADT システム用のパーティ情報を構成します。  
  
### <a name="to-configure-the-adt-system-party-information"></a>ADT システム パーティ情報を構成するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。  
  
2.  パーティのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**Tutorial_ADTSystem**です。 (このボックスに入力した値は、元の HL7 メッセージ インスタンス ADT^A03.txt MSH3 は) です。  
  
3.  コンソール ツリーでクリックして**送信ポート**です。  
  
4.  送信ポート] ペインで [空白のフィールドをクリックして、**名前**列で、選択**Tutorial_sendAck_ADT**、クリックして**[ok]**です。  
  
5.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、クリックして**BTAHL7 構成エクスプ ローラー**です。  
  
6.  BTAHL7 構成エクスプ ローラーで、選択、**受信確認**タブです。**受信確認の種類** **EnhancedMode**です。  
  
7.  をクリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。  
  
 進みます[手順 8B: RX システム用のパーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md)です。