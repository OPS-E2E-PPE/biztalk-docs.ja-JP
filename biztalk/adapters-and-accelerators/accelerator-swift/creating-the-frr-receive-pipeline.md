---
title: 受信パイプラインの作成、FRR |Microsoft ドキュメント
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
ms.openlocfilehash: ad31a69d579cf2bbe9f646fc87be1bea9f561a10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210378"
---
# <a name="creating-the-frr-receive-pipeline"></a>受信パイプラインの FRR の作成
FIN 対応調整を実行するには、SWIFT FRR デコーダーと SWIFT の逆アセンブラーに加え、SWIFT FRR 相互関係セット競合回避モジュールのパイプライン コンポーネントを含む受信パイプラインを作成する必要があります。  
  
 **概要**  
  
 次のステージ/プロパティで、受信パイプラインを作成します。  
  
|ステージ/プロパティ|コンポーネント/設定|  
|---------------------|------------------------|  
|逆アセンブル ステージ|SWIFT 逆アセンブラー|  
|BRE の検証プロパティ (SWIFT 逆アセンブラー)|True|  
|XML 検証プロパティ (SWIFT 逆アセンブラー)|True|  
|SWIFT ヘッダー スキーマ プロパティ (SWIFT 逆アセンブラー)|(なし)|  
|デコーダーのステージ|SWIFT FRR MQSeries デコーダー|  
|パーティの解決ステージ|SWIFT FRR 相関関係の設定の競合回避モジュール|  
  
### <a name="to-create-a-custom-receive-pipeline-for-frr"></a>FRR のカスタム受信パイプラインを作成するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio で、含まれているプロジェクトを右クリックし、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]パイプライン、順にポイント**追加**、クリックして**新しい項目の**します。  
  
2.  新しい項目の追加 ダイアログ ボックスで、**パイプライン ファイル**カテゴリ ウィンドウで、選択**受信パイプライン**テンプレート ペインでします。  
  
3.  **名前**ボックスで、受信パイプラインの名前を入力します。 **FRRReceivePipeline.btp**です。 **[追加]** をクリックします。  
  
    > [!NOTE]
    >  追加する必要があります手順 4. を実行する前に、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 」の説明に従って、FRR がツールボックスにコンポーネントをパイプライン[をツールボックスに SWIFT パイプライン コンポーネントを追加する](../../adapters-and-accelerators/accelerator-swift/adding-swift-pipeline-components-to-the-toolbox.md)です。  
  
4.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ビュー** をクリックし、**ツールボックス**です。  
  
5.  BizTalk パイプライン コンポーネント [ツールボックス] ウィンドウからドラッグ、 **SWIFT 逆アセンブラー**を**ここにドロップ**下のボックス、**逆アセンブル**パイプライン デザイナーで図形をステージです。  
  
6.  **SWIFT 逆アセンブラー コンポーネント**でパイプライン デザイナーで選択した**プロパティ**、いることを確認、 **BRE 検証**と**XML 検証**プロパティに設定されます**True**、および**SWIFT ヘッダー スキーマ**プロパティに設定されている **(なし)** です。  
  
7.  BizTalk パイプライン コンポーネント [ツールボックス] で、ドラッグ**SWIFT FRR MQSeries デコーダー**を**ここにドロップ**下のボックス、**デコーダー**パイプライン デザイナーで図形をステージです。  
  
8.  BizTalk パイプライン コンポーネント [ツールボックス] ウィンドウからドラッグ**SWIFT FRR 相関関係設定の競合回避モジュール**を**ここにドロップ**下のボックス、**パーティの解決**パイプライン内の図形をステージデザイナー。  
  
9. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ファイル**、順にクリック**すべてを保存**です。