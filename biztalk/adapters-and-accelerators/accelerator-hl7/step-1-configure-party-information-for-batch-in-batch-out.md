---
title: "手順 1: バッチのバッチにするためのパーティ情報の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a93d774b-1282-40d9-836f-44abeb65f78e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 982b17fe3826a0e5c5ee2a42030ba020b755ab70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a>手順 1: 構成内のバッチの情報をパーティ/アウト バッチ
バッチを有効にすると、パーティのバッチ処理の断片化をオフにするこの手順でのシナリオをバッチ処理/です。 再起動する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を有効にする構成の変更を有効にします。  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a>パーティのバッチ処理の断片化をオフにするには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン > Accelerator 用 HL7**、クリックして**BTAHL7構成のエクスプ ローラー**です。  
  
2.  BTAHL7 構成エクスプ ローラーで、上、**パーティ**、左側のウィンドウ タブで、をクリックして**Tutorial_BatchSource**です。  
  
3.  クリックして、**バッチ定義**タブです。  
  
4.  選択**いいえ**の**断片化のために必要な**、順にクリック**保存**です。  
  
5.  ことを確認して**回復可能なインターチェンジのサポートに必要な**ドロップ ダウン リスト**False**が選択されています。  
  
 進みます[手順 2: 変更または作成、送信ポートと受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)です。