---
title: "手順 3: を作成し、送信先パーティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8746f115-9f69-4593-9943-9ccda45cd900
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34fb3ef45123817f747ab9aa956e961c5bb9a1c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-and-configure-a-destination-party"></a>手順 3: を作成し、送信先パーティを構成します。
このステップでは、作成し、バッチの作成シナリオでは、送信先パーティを構成します。 選択することも、メッセージを[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]バッチとバッチのスケジュールは、そのパーティ用に定義されています。 フォルダーにファイルをコピーした後で 1 時間に 1 つのバッチ送信時間をスケジュールするとします。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]その後 1 時間の頻度での受信メッセージをバッチ処理します。  
  
### <a name="to-create-and-configure-a-destination-party"></a>作成し、送信先パーティを構成します。  
  
1.  BizTalk Server 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。  
  
2.  パーティのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**Tutorial_BatchDest**、順にクリック**ok**です。  
  
3.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン > Accelerator 用 HL7**、クリックして**BTAHL7構成のエクスプ ローラー**です。  
  
4.  BTAHL7 構成エクスプ ローラーで、上、**パーティ**コンソール ツリーで、タブをクリックし**Tutorial_BatchDest**です。  
  
5.  クリックして、**受信確認** タブで、詳細ウィンドウ。 いることを確認、**受信確認の種類**は**None**です。  
  
6.  クリックして、**バッチ定義**タブです。**使用可能なメッセージ**ペインで、 **BTAHL7Schemas.ADT_A03_231_GLO_DEF**です。 右矢印を移動 をクリックして (**>>**) に、このスキーマを追加する**選択したメッセージを**、順にクリック**保存**です。  
  
7.  クリックして、**バッチ スケジュール**タブです。**後にバッチを繰り返して**セクションであることを確認**時間**が選択されているし、入力**1**で、**時間**ボックス。 **最初のバッチになるまで時間**ボックスに、入力**1**、クリックして**スケジュールの開始**です。  
  
 進みます[手順 4: 作成バッチ シナリオでは、送信元パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)です。