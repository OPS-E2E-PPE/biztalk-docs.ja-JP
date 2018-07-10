---
title: 受信パイプラインの作成、FRR |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive pipelines, creating
- FRR, creating receive pipelines
- creating, receive pipelines
ms.assetid: 5884176b-8522-4dd3-8f93-8695858b59ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbf4e735019c5399e1b7f1648f3adbcffe18fed2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970803"
---
# <a name="creating-the-frr-receive-pipeline"></a>作成、FRR 受信パイプライン
FIN Response Reconciliation を実行するには、SWIFT FRR デコーダーと SWIFT 逆アセンブラーに加え、SWIFT FRR CorrelationSet 競合回避モジュールのパイプライン コンポーネントを含む受信パイプラインを作成する必要があります。  

 **概要**  

 次のステージ/プロパティを持つ受信パイプラインを作成します。  

|ステージ/プロパティ|コンポーネント/設定|  
|---------------------|------------------------|  
|逆アセンブル ステージ|SWIFT 逆アセンブラー|  
|BRE の検証プロパティ (SWIFT 逆アセンブラー)|True|  
|XML 検証プロパティ (SWIFT 逆アセンブラー)|True|  
|SWIFT ヘッダー スキーマ プロパティ (SWIFT 逆アセンブラー)|(なし)|  
|デコーダーのステージ|SWIFT FRR MQSeries デコーダー|  
|パーティの解決ステージ|SWIFT FRR 関連付けセットの競合回避モジュール|  

### <a name="to-create-a-custom-receive-pipeline-for-frr"></a>FRR のカスタム受信パイプラインを作成するには  

1. ソリューション エクスプ ローラーの Visual Studio でプロジェクトを含むを右クリックし、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]パイプラインが指す**追加**、順にクリックします**新しい項目の**します。  

2. [新しい項目の追加] ダイアログ ボックスで、**パイプライン ファイル**カテゴリ] ウィンドウで選択し**受信パイプライン**テンプレート] ペインでします。  

3. **名前**など、受信パイプラインの名前を入力ボックスに、 **FRRReceivePipeline.btp**します。 **[追加]** をクリックします。  

   > [!NOTE]
   >  手順 4 を実行する前に追加する必要があります、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 」の説明に従って、FRR がツールボックスにコンポーネントをパイプライン[をツールボックスに SWIFT パイプライン コンポーネントを追加する](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md)します。  

4. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、] をクリックして**ビュー**し**ツールボックス**します。  

5. BizTalk パイプライン コンポーネントのツールボックス ウィンドウからドラッグ、 **SWIFT 逆アセンブラー**を**ここにドロップ**下のボックス、**逆アセンブル**パイプライン デザイナーで図形をステージングします。  

6. **SWIFT 逆アセンブラー コンポーネント**でパイプライン デザイナーで選択されている**プロパティ**、いることを確認、 **BRE 検証**と**XMLの検証**プロパティに設定されます**True**、および**SWIFT ヘッダー スキーマ**プロパティに設定されて **(なし)** します。  

7. BizTalk パイプライン コンポーネントのツールボックスのドラッグ**SWIFT FRR MQSeries デコーダー**を**ここにドロップ**下のボックス、**デコーダー**パイプライン デザイナーで図形をステージングします。  

8. BizTalk パイプライン コンポーネントのツールボックス ウィンドウからドラッグ**SWIFT FRR 相関設定リゾルバー**を**ここにドロップ**下のボックス、**パーティの解決**パイプライン内の図形をステージデザイナー。  

9. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、] をクリックして**ファイル**、] をクリックし、**すべて保存**します。
