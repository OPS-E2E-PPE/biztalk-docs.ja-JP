---
title: "A4SWIFT のスキーマを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, A4SWIFT
- deploying, A4SWIFT schemas
- A4SWIFT, deploying schemas
- schemas, deploying
ms.assetid: a6aed2cd-3578-442e-ab1e-8284cc5f7b72
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 331a21c64aa0130b3e110f1da6ca776f0b2c6a49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-a4swift-schemas"></a>A4SWIFT のスキーマを展開します。
交換する SWIFT メッセージのスキーマを展開する必要があります。  
  
 **概要**  
  
 次のスキーマを展開します。  
  
-   SWIFT 基本 Types.xsd  
  
-   SWIFT の一般的なデータ Types.xsd  
  
-   メッセージ型、MT103.xsd などの特定のスキーマ  
  
### <a name="to-create-a-strong-named-swift-project"></a>厳密な名前の SWIFT プロジェクトを作成するには  
  
1.  Visual Studio で、**ファイル**、をポイント**新規**、クリックして**プロジェクト**です。  
  
2.  新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**ペインで、 **BizTalk プロジェクト**フォルダーです。  
  
3.  **テンプレート**ペインで、**空の BizTalk Server プロジェクト**です。  
  
4.  **名前**ボックスで、プロジェクト名の名前を入力します。  
  
5.  **ソリューション**ボックスで、**新しいソリューションを作成**です。 **場所**ボックスに、スキーマにプロジェクトを追加するプロジェクトの場所を入力します。  
  
6.  をクリックして**OK**新しいプロジェクトを開きます。  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ソリューション エクスプ ローラーに新しいプロジェクトを追加し、指定されたフォルダーにプロジェクト フォルダーとファイルを作成します。  
  
7.  Visual Studio コマンド プロンプトを起動します。  
  
8.  Visual Studio コマンド プロンプトを参照  **\<*ドライブ*>: \Program Files\Microsoft BizTalk Accelerator for SWIFT * *。  
  
9. コマンド プロンプトで次のように入力します。 **sn – k key.snk**、ENTER キーを押します。 キーのペアが key.snk に書き込まれたことを示すコマンド プロンプト ウィンドウで、メッセージが表示されることを確認します。  
  
10. ソリューション エクスプ ローラーで、プロジェクト名を右クリックし、をクリックして**プロパティ**です。  
  
11. 左側のウィンドウで、**プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ**です。  
  
12. 右側のペインで、**プロパティ ページ**を下にスクロール ダイアログ ボックスで、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、をクリックし、省略記号ボタン () ボタンをクリックします。  
  
13. **アセンブリ キー ファイル**ダイアログ ボックスを参照  **\<*ドライブ*>: \Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)]をクリックして**key.snk**、クリックして**開く**です。  
  
14. **プロパティ ページ**ダイアログ ボックスで、をクリックして**OK**変更を保存します。  
  
### <a name="to-add-a-swift-schema"></a>SWIFT スキーマに追加するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio でプロジェクトを開きます。  
  
2.  プロジェクトを右クリックし、順にポイント**追加**、クリックして**既存項目の**します。  
  
3.  **既存項目の追加** ダイアログ ボックスで、:\\**files \microsoft BizTalk Accelerator for SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Base スキーマ**です。 選択、 **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**スキーマ、およびクリック**追加**です。  
  
4.  プロジェクトを右クリックし、順にポイント**追加**、クリックして**既存項目の追加**です。  
  
5.  **既存項目の追加** ダイアログ ボックスで、**ファイルの場所**ドロップダウン ボックスに移動**\<ドライブ >: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT \<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Category n\MTxxx**です。 インスタンス メッセージの種類のスキーマを選択**MT103.xsd**、クリックして**追加**です。  
  
    > [!NOTE]
    >  ソリューション エクスプ ローラーで示すように、A4SWIFT は、プロジェクトのスキーマを追加します。  
  
6.  ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**ビルド**です。  
  
7.  ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**展開**です。