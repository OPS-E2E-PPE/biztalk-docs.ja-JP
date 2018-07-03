---
title: '手順 8 a: ADT System 用にパーティ情報の構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0d750c2-a3c6-4571-a4e1-0d0aaaa4d400
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c1a608571c9cc3f939f9387c2e3a113273af554
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969763"
---
# <a name="step-8a-configure-party-information-for-the-adt-system"></a>手順 8 a: ADT System 用にパーティ情報を構成します。
この手順では、ADT System 用のパーティ情報を構成します。  
  
### <a name="to-configure-the-adt-system-party-information"></a>ADT System パーティ情報を構成するには  
  
1. 右クリックし、BizTalk Server 管理コンソールで**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**。  
  
2. パーティのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **Tutorial_ADTSystem**します。 (このボックスに入力した値は、元の HL7 メッセージ インスタンス ADT^A03.txt MSH3 は) です。  
  
3. コンソール ツリーで、クリックして**送信ポート**します。  
  
4. 送信ポート] ペインで、[空白のフィールドをクリックします。、**名前**列で、 **Tutorial_sendAck_ADT**、順にクリックします**OK**します。  
  
5. クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、順にクリックします**BTAHL7 構成エクスプ ローラー**します。  
  
6. BTAHL7 構成エクスプ ローラーで、**受信確認**タブ。**受信確認の種類**、 **EnhancedMode**します。  
  
7. クリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。  
  
   続行する[手順 8 b: RX System 用にパーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md)します。