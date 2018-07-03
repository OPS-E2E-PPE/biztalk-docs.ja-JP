---
title: '手順 3: を作成し、送信先パーティを構成する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8746f115-9f69-4593-9943-9ccda45cd900
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 086f2ff18db68651187e1b7392d5995f231234c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997867"
---
# <a name="step-3-create-and-configure-a-destination-party"></a>手順 3: を作成し、送信先パーティを構成します。
この手順では、作成し、バッチの作成シナリオでは、送信先パーティを構成します。 選択することも、メッセージを[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]バッチとバッチ スケジュール、そのパーティに対して定義されています。 フォルダーにファイルをコピーした後 1 時間に 1 つのバッチ送信時間をスケジュールします。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] その後 1 時間の頻度での受信メッセージをバッチ処理します。  
  
### <a name="to-create-and-configure-a-destination-party"></a>作成して送信先パーティを構成するには  
  
1. 右クリックし、BizTalk Server 管理コンソールで**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**。  
  
2. パーティのプロパティ ダイアログ ボックスで、**名前**ボックスに「 **Tutorial_BatchDest**、順にクリックします**OK**します。  
  
3. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**をクリックして**BTAHL7 構成エクスプ ローラー**します。  
  
4. BTAHL7 構成エクスプ ローラーでの**パーティ**コンソール ツリーで、タブをクリックして**Tutorial_BatchDest**します。  
  
5. をクリックして、**受信確認**詳細ペインでタブ。 いることを確認、**受信確認の種類**は**None**します。  
  
6. をクリックして、**バッチ定義**タブ。**使用可能なメッセージ**ペインで、 **BTAHL7Schemas.ADT_A03_231_GLO_DEF**します。 右矢印を移動 をクリックして (**>>**) に、このスキーマを追加する**選択したメッセージを**、順にクリックします**保存**します。  
  
7. をクリックして、**バッチ スケジュール**タブ。**後にバッチを繰り返す**セクションで、いることを確認**時間**が選択されているし、入力**1**で、**時間**ボックス。 **時間前最初のバッチに**ボックスに「 **1**、順にクリックします**開始スケジュール**します。  
  
   進みます[手順 4: バッチの作成シナリオでは、送信元パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)します。