---
title: '手順 1: バッチのバッチでアウト用にパーティ情報の構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a93d774b-1282-40d9-836f-44abeb65f78e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eafe692cf86ccf3c6fbe0713c1e621a99a601d5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974923"
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a>手順 1: 構成でバッチ用にパーティ情報/バッチ アウト
バッチを有効にすると、パーティのバッチ処理の断片化をオフにするこの手順で/バッチ アウト シナリオ。 再起動する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を有効にする構成変更を有効にします。  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a>パーティのバッチ処理の断片化をオフにするには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**をクリックして**BTAHL7 構成エクスプ ローラー**します。  
  
2. BTAHL7 構成エクスプ ローラーでの**パーティ**左側のウィンドウ] タブで [ **Tutorial_BatchSource**。  
  
3. をクリックして、**バッチ定義**タブ。  
  
4. 選択**いいえ**の**断片化のために必要な**、順にクリックします**保存**します。  
  
5. 確認します**回復可能なインターチェンジ サポート必要**ドロップダウン リスト**False**が選択されています。  
  
   続行する[手順 2: 変更または作成、送信ポートと受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)します。