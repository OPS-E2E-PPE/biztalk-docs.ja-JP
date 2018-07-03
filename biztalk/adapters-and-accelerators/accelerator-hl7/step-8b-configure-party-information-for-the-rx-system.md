---
title: '手順 8 b: RX System 用にパーティ情報の構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b0b34ec9-220d-4a6b-9712-54c8099b663b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2ed8dfaeb333c1b35ea64a5d52a53ebce509729
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008403"
---
# <a name="step-8b-configure-party-information-for-the-rx-system"></a>手順 8 b: RX System 用にパーティ情報を構成します。
この手順では、RX System 用のパーティ情報を構成します。  

### <a name="to-configure-the-rx-system-party-information"></a>RX System パーティ情報を構成するには  

1. 右クリックし、BizTalk Server 管理コンソールで**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**。  

2. パーティのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **Tutorial_RXSystem**します。  

3. コンソール ツリーで、クリックして**送信ポート**します。  

4. 送信ポート] ペインで、[空白のフィールドをクリックします。、**名前**列で、 **Tutorial_sendMsg_RX**、順にクリックします**OK**します。  

5. クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、順にクリックします**BTAHL7 構成エクスプ ローラー**します。  

6. BTAHL7 構成エクスプ ローラーで、 **MSH マップ**タブをクリックし、次の操作を行います。  


   | プロパティ |                    目的                    |
   |----------|--------------------------------------------------|
   | **MSH3** |      型**BTAHL7**左側のテキスト ボックス。       |
   | **MSH5** | 型**Tutorial_RXSystem**左側のテキスト ボックス。 |


7. クリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。  

   続行する[手順 8 C: HI System 用にパーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md)します。