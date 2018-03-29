---
title: '手順 3: トリガー イベント (メッセージ) のスキーマを追加する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc4a67d9-9582-4f2b-9bc9-18fbff823d29
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 439caac8f1da151a9f203a1372039aaeedbfe83c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="step-3-add-a-trigger-event-message-schema"></a>手順 3: トリガー イベント (メッセージ) のスキーマを追加します。
この手順で、空に基づく新しいプロジェクトを作成する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]プロジェクト テンプレート。 このプロジェクトにスキーマを追加する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信のバッチ内のメッセージの検証に使用されます (ADT ^ A03)。 プロジェクトに厳密な名前を割り当てる、および、プロジェクトを配置 v2.3.1 一般的なスキーマを含むプロジェクトへの参照を追加します。  
  
### <a name="to-add-the-project-containing-the-message-schema"></a>メッセージ スキーマを含むプロジェクトを追加するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  
  
2.  新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**です。  
  
3.  **テンプレート**セクションで、 **BTAHL7 の空のプロジェクト**です。  
  
4.  **名前**ボックスに、入力**BTAHL7V231Body**プロジェクト名として。  
  
5.  **ソリューション**ボックスで、**ソリューションに追加**です。  
  
6.  **[OK]**をクリックします。  
  
7.  ソリューション エクスプ ローラーで、新しいプロジェクトのノードの下を右クリックして**参照**、クリックして**参照の追加**です。  
  
8.  参照の追加 ダイアログ ボックスで、**プロジェクト** タブで、をクリックして**BTAHL7V231Common プロジェクト**で、**プロジェクト名**列で、をクリックして**追加**、クリックして**OK**です。  
  
### <a name="to-add-the-schema-to-the-project"></a>スキーマをプロジェクトに追加するには  
  
1.  ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body**、 をポイント**追加**、クリックして**新しい項目の**します。  
  
2.  [新しい項目の追加] ダイアログ ボックスで、展開**BizTalk プロジェクトの項目**、クリックして**BTAHL7 スキーマ**です。 **テンプレート** ウィンドウで、をクリックして**BTAHL7 スキーマ**、クリックして**追加**です。  
  
3.  **HL7 スキーマの選択** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Message クラス**|保持**V2.X**として選択します。|  
    |**[バージョン]**|選択**2.3.1**です。|  
    |**メッセージの種類**|選択**ADT**です。|  
    |**トリガー イベント**|選択**A03**です。|  
  
4.  をクリックして**作成**をプロジェクトにスキーマを追加、をクリックして**キャンセル** ダイアログ ボックスを閉じます。 注その BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) が、BTAHL7V231Body プロジェクトには、ADT_A03_231_GLO_DEF.xsd スキーマを追加します。  
  
### <a name="to-assign-a-strong-key-and-deploy"></a>強力なキーを割り当てるし、展開するには  
  
1.  ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body**、クリックして**プロパティ**です。  
  
2.  BTAHL7V231Body プロパティ ページ ダイアログ ボックスで、**署名**です。  
  
3.  確認**アセンブリに署名**チェック ボックスをオンします。  
  
4.  **厳密な名前キー ファイルを選択して**ドロップ ダウン リストを**\<を参照しています.\>.**  
  
5.  参照 **\<*ドライブ*\>: \Batching チュートリアル** **key.snk**、順にクリック**開く**です。  
  
6.  ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body**、クリックして**展開**です。 成功メッセージが出力ウィンドウに表示されることを確認します。  
  
    > [!NOTE]
    >  Successful-deploy メッセージが表示されない場合を使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマをトラブルシューティングします。  
  
 進みます[手順 4: 作成、バッチ メッセージを受け入れるための受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)です。