---
title: 作成して、A4SWIFT パイプラインを展開する |Microsoft ドキュメント
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
ms.openlocfilehash: bec21ebd5a3b32986969676a78109cad55d870cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210954"
---
# <a name="creating-and-deploying-a4swift-pipelines"></a>作成して、A4SWIFT パイプラインを展開します。
次の図に示すように作成し、メッセージ repair and new submission の SWIFT パイプラインを展開するには、次の手順を実行します。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")  
  
 **概要**  
  
 次のスキーマを展開します。  
  
-   カスタムは、SWIFT 逆アセンブラのパイプラインが表示されます。 BRE の検証および XML プロパティを設定すると、True、かつ、SWIFT ヘッダー スキーマ プロパティを (なし)。  
  
-   カスタム送信パイプラインに SWIFT アセンブラー  
  
### <a name="to-create-a-pipeline-project"></a>パイプライン プロジェクトを作成するには  
  
1.  Visual Studio で、[**ファイル**、] をポイント**新規**、クリックして**プロジェクト**です。  
  
2.  新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**ペインで、 **BizTalk プロジェクト**フォルダーです。  
  
3.  **テンプレート**ペインで、**空の BizTalk Server プロジェクト**です。  
  
4.  **名前**ボックスで、プロジェクト名の名前を入力します。  
  
5.  **ソリューション**ボックスで、**ソリューションに追加**です。 **場所**ボックスで作成したスキーマ プロジェクトの場所を入力[A4SWIFT のスキーマを展開する](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)です。  
  
6.  をクリックして**OK**新しいプロジェクトを開きます。  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ソリューション エクスプ ローラーに新しいプロジェクトを追加し、指定されたフォルダーにプロジェクト フォルダーとファイルを作成します。  
  
7.  作成し、強力なキー ファイルをプロジェクトに割り当てます。 詳細についてを参照してください「プロジェクトを作成する、厳密な名前 SWIFT」 [A4SWIFT のスキーマを展開する](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)です。  
  
### <a name="to-add-a-custom-receive-pipeline"></a>カスタム受信パイプラインを追加するには  
  
1.  ソリューション エクスプ ローラーで、パイプライン プロジェクトを右クリックし、**追加**、クリックして**新しい項目の**します。  
  
2.  新しい項目の追加 ダイアログ ボックスで、**パイプライン ファイル**カテゴリ ウィンドウで、選択**受信パイプライン**テンプレート ペインからです。  
  
3.  **名前**ボックスで、パイプラインの名前を入力します。  
  
4.  をクリックして**追加**BizTalk パイプライン デザイナーで空白のパイプラインを開きます。  
  
5.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ビュー**し**ツールボックス**です。  
  
6.  **BizTalk パイプライン コンポーネントのツールボックス**、ドラッグ、 **SWIFT 逆アセンブラー**を**ここにドロップ**下のボックス、**逆アセンブル**ステージ図形に**BizTalk パイプライン デザイナ**です。 ままにして、 **SWIFT 逆アセンブラー**で選択されて、 **BizTalk パイプライン デザイナ**です。  
  
7.  **プロパティ**、いることを確認、 **BRE 検証**と**XML 検証**プロパティに設定されます**True**です。  
  
    > [!NOTE]
    >  SWIFT ヘッダー スキーマ プロパティを設定する必要があります **(なし)** です。  
  
8.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ファイル**、し**すべてを保存**です。  
  
### <a name="to-add-a-custom-send-pipeline"></a>カスタム送信パイプラインを追加するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。  
  
2.  新しい項目の追加 ダイアログ ボックスであることを確認**パイプライン ファイル**が選択されてカテゴリ ウィンドウで、**送信パイプライン**テンプレート ペインからです。  
  
3.  **名前**ボックスで、パイプラインの名前を入力します。  
  
4.  をクリックして**追加**BizTalk パイプライン デザイナーで空白のパイプラインを開きます。  
  
    > [!NOTE]
    >  BizTalk パイプライン デザイナーで空のパイプラインが表示されます。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーに SWIFTPipelines プロジェクトの下で、新しいパイプラインを追加します。  
  
5.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ビュー**し**ツールボックス**です。  
  
6.  **BizTalk パイプライン コンポーネントのツールボックス**、ドラッグ**SWIFT アセンブラー**を**ここにドロップ**下のボックス、**アセンブル**で図形をステージ**BizTalk パイプライン デザイナ**です。  
  
7.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ファイル**、し**すべてを保存**です。  
  
8.  パイプライン プロジェクトを右クリックし、をクリックして**ビルド**です。  
  
    > [!NOTE]
    >  コンパイル プロセス中に表示しないようにすべてのエラーです。 場合は、エラーの原因を確認して修正して、プロジェクトを再構築します。 ただし、警告が表示、可能性があります。 警告を引き起こす状況を修正することができます。 詳細についてを参照してください「パイプライン プロジェクトをビルドすることがありますで警告を表示」[その他の既知の問題](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)です。  
  
9. パイプライン プロジェクトを右クリックし、をクリックして**展開**です。