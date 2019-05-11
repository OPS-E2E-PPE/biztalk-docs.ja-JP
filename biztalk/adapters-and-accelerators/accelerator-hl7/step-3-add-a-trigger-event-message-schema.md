---
title: 手順 3:トリガー イベント (メッセージ) スキーマの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc4a67d9-9582-4f2b-9bc9-18fbff823d29
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c395a5dd68686b04d47af790f733174787b5a4b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288891"
---
# <a name="step-3-add-a-trigger-event-message-schema"></a>手順 3:トリガー イベント (メッセージ) スキーマを追加します。
この手順で、空に基づく新しいプロジェクトを作成する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]プロジェクト テンプレート。 このプロジェクトにスキーマを追加する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信バッチ内のメッセージの検証に使用されます (ADT ^ A03)。 V2.3.1 の一般的なスキーマを含むプロジェクトへの参照を追加し、プロジェクトに厳密な名前を割り当て、プロジェクトを配置します。  

### <a name="to-add-the-project-containing-the-message-schema"></a>メッセージ スキーマを含むプロジェクトに追加するには  

1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  

2. 新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**セクションで、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。  

3. **テンプレート**セクションで、 **BTAHL7 の空のプロジェクト**します。  

4. **名前**ボックスに、入力**BTAHL7V231Body**プロジェクト名として。  

5. **ソリューション**ボックスで、**ソリューションに追加**します。  

6. **[OK]** をクリックします。  

7. ソリューション エクスプ ローラーで、新しいプロジェクトのノードで右クリック**参照**、 をクリックし、**参照の追加**します。  

8. 参照の追加 ダイアログ ボックスで、上、**プロジェクト** タブで  **BTAHL7V231Common プロジェクト**で、**プロジェクト名**列、 をクリックして**追加**、クリックして**OK**します。  

### <a name="to-add-the-schema-to-the-project"></a>スキーマをプロジェクトに追加するには  

1. ソリューション エクスプ ローラーで右クリック**BTAHL7V231Body**、 をポイント**追加**、 をクリックし、**新しい項目の**します。  

2. 新しい項目の追加 ダイアログ ボックスで、 **BizTalk プロジェクトの項目**、 をクリックし、 **BTAHL7 スキーマ**します。 **テンプレート**ウィンドウで、をクリックして**BTAHL7 スキーマ**、 をクリックし、**追加**。  

3. **HL7 スキーマの選択** ダイアログ ボックスで、次の操作を行います。  


   |     プロパティ      |         目的         |
   |-------------------|----------------------------|
   | **Message クラス** | 保持**V2.X**として選択します。 |
   |    **バージョン**    |     選択**2.3.1**します。      |
   | **メッセージの種類**  |      選択**ADT**します。       |
   | **トリガー イベント** |      選択**A03**します。       |


4. をクリックして**作成**をプロジェクトにスキーマを追加する をクリックし、**キャンセル**ダイアログ ボックスを閉じます。 注その BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) が BTAHL7V231Body プロジェクトに ADT_A03_231_GLO_DEF.xsd スキーマを追加します。  

### <a name="to-assign-a-strong-key-and-deploy"></a>強力なキーの割り当てをデプロイします。  

1. ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Body**、 をクリックし、**プロパティ**します。  

2. BTAHL7V231Body プロパティ ページ] ダイアログ ボックスで、[**署名**します。  

3. 確認**アセンブリに署名**チェック ボックスをオンします。  

4. **厳密な名前キー ファイルを選択して**一覧選択ドロップダウン**\<を参照しています.\>.**  

5. 参照 **\<*ドライブ*\>: \Batching チュートリアル**を選択します**key.snk**、 をクリックし、**オープン**します。  

6. ソリューション エクスプ ローラーで右クリックして**BTAHL7V231Body**、 をクリックし、**デプロイ**します。 成功メッセージが出力ウィンドウに表示されることを確認します。  

   > [!NOTE]
   >  Successful-deploy メッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]スキーマのトラブルシューティングを行う。  

   続行する[手順 4。作成、受信ポートのバッチ メッセージを受け入れる](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)します。