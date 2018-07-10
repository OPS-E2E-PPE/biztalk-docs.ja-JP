---
title: A4SWIFT パイプラインの作成と |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- deploying, pipelines
- pipelines, deploying
- pipelines, creating
ms.assetid: 2a614510-7e15-4e88-9012-fc019d3aefee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d337b97dfb1973ef10c113ae0a206a51dcd63b1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002451"
---
# <a name="creating-and-deploying-a4swift-pipelines"></a>A4SWIFT パイプラインの作成と
次の図に示すように作成してメッセージ repair and new submission は、SWIFT パイプラインをデプロイするには、次の手順を実行します。  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")  

 **概要**  

 次のスキーマを展開します。  

-   カスタムの受信、SWIFT 逆アセンブラーをパイプラインします。 True、SWIFT ヘッダー スキーマ プロパティを (None) には、BRE の検証および XML の検証のプロパティを設定します。  

-   カスタム送信パイプラインに SWIFT アセンブラー  

### <a name="to-create-a-pipeline-project"></a>パイプライン プロジェクトを作成するには  

1. Visual Studio で、次のようにクリックします。**ファイル**、 をポイント**新規**、 をクリックし、**プロジェクト**します。  

2. 新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**ペインで、 **BizTalk プロジェクト**フォルダー。  

3. **テンプレート**ペインで、**空の BizTalk Server プロジェクト**します。  

4. **名前**ボックスで、プロジェクト名の名前を入力します。  

5. **ソリューション**ボックスで、**ソリューションに追加**します。 **場所**ボックスで作成したスキーマ プロジェクトの場所を入力[A4SWIFT スキーマの展開](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)します。  

6. をクリックして**OK**を新しいプロジェクトを開きます。  
   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] ソリューション エクスプ ローラーに新しいプロジェクトを追加し、指定したフォルダーで、プロジェクト フォルダーとファイルを作成します。  

7. 作成し、厳密なキー ファイルをプロジェクトに割り当てます。 詳細についてを参照してください「厳密な名前の SWIFT プロジェクトを作成するには" [A4SWIFT スキーマの展開](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)します。  

### <a name="to-add-a-custom-receive-pipeline"></a>カスタム受信パイプラインを追加するには  

1. ソリューション エクスプ ローラーで、パイプライン プロジェクトを右クリックして**追加**、 をクリックし、**新しい項目の**します。  

2. 新しい項目の追加 ダイアログ ボックスで、**パイプライン ファイル**カテゴリ ウィンドウで選択し**受信パイプライン**テンプレート ペインから。  

3. **名前**ボックスに、パイプラインの名前を入力します。  

4. クリックして**追加**に BizTalk パイプライン デザイナで、空のパイプラインを開きます。  

5. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、] をクリックして**ビュー**し**ツールボックス**します。  

6. **BizTalk パイプライン コンポーネントのツールボックス**、ドラッグ、 **SWIFT 逆アセンブラー**を**ここにドロップ**下のボックス、**逆アセンブル**ステージ図形に**BizTalk パイプライン デザイナ**します。 ままに、 **SWIFT 逆アセンブラー**として選択された状態で、 **BizTalk パイプライン デザイナ**します。  

7. **プロパティ**、いることを確認、 **BRE 検証**と**XML 検証**プロパティに設定されます**True**します。  

   > [!NOTE]
   >  SWIFT ヘッダー スキーマ プロパティに設定する必要があります **(なし)** します。  

8. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、] をクリックして**ファイル**、し**すべて保存**します。  

### <a name="to-add-a-custom-send-pipeline"></a>カスタム送信パイプラインを追加するには  

1. ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。  

2. 新しい項目の追加 ダイアログ ボックスであることを確認**パイプライン ファイル**がカテゴリ ウィンドウで選択されて **送信パイプライン**テンプレート ペインから。  

3. **名前**ボックスに、パイプラインの名前を入力します。  

4. クリックして**追加**に BizTalk パイプライン デザイナで、空のパイプラインを開きます。  

   > [!NOTE]
   >  BizTalk パイプライン デザイナーで空のパイプラインが表示されます。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] ソリューション エクスプ ローラーに SWIFTPipelines プロジェクトの下の新しいパイプラインを追加します。  

5. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、] をクリックして**ビュー**し**ツールボックス**します。  

6. **BizTalk パイプライン コンポーネントのツールボックス**、ドラッグ**SWIFT アセンブラー**を**ここにドロップ**下のボックス、**アセンブル**で図形をステージ**BizTalk パイプライン デザイナ**します。  

7. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、] をクリックして**ファイル**、し**すべて保存**します。  

8. パイプライン プロジェクトを右クリックし、をクリックし、**ビルド**します。  

   > [!NOTE]
   >  コンパイル プロセス中にいない、エラーが発生する必要があります。 場合は、エラーの原因を確認、修正およびプロジェクトを再ビルドします。 ただし、警告が表示、可能性があります。 警告につながる条件を修正することができます。 詳細についてを参照してください「で警告結果がパイプライン プロジェクトのビルド」[その他の既知の問題](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)します。  

9. パイプライン プロジェクトを右クリックし、をクリックし、**デプロイ**します。
