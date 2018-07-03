---
title: '手順 7: を作成し、送信元パーティの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8788a9c-ae6f-461b-82e5-f4276d1d5e0c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4708a682047ced4fa33ae34781fd88d379c5e70b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968931"
---
# <a name="step-7-create-and-configure-a-source-party"></a>手順 7: を作成し、送信元パーティの構成
この手順では、ソース パーティを構成し、送信ポート、送信メッセージのメッセージ ヘッダーの変換を有効にするを割り当てますを作成します。  
  
### <a name="to-create-and-configure-a-source-party"></a>作成および送信元パーティを構成するには  
  
1. BizTalk 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**します。  
  
2. **パーティ プロパティ**ダイアログ ボックスで、名前フィールドに、型**Tutorial_BatchSource**します。  
  
   > [!NOTE]
   >  このボックスに入力した値が、元の FHS3.1 から[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]FragmentedInboundBatch.txt バッチのメッセージ。  
  
3. コンソール ツリーで、クリックして**送信ポート**します。  
  
4. 送信ポート ペインで、名前フィールドに、次のように選択します。 **Tutorial_2wayAck**します。  
  
5. **[OK]** をクリックします。  
  
6. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**をクリックして**BTAHL7 構成エクスプ ローラー**します。  
  
7. BTAHL7 構成エクスプ ローラーでの**パーティ**] タブで [ **Tutorial_BatchSource**します。  
  
8. 選択、**バッチ定義**BTAHL7 構成エクスプ ローラーのタブ。 選択**はい**の**断片化のために必要な**、順にクリックします**保存**します。  
  
9. 選択、**受信確認**タブ。**受信確認の種類**を選択します**OriginalMode**、 をクリックし、**保存**します。  
  
   続行する[手順 8: BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)します。