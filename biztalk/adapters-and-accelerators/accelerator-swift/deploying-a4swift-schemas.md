---
title: A4SWIFT のスキーマを展開する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, A4SWIFT
- deploying, A4SWIFT schemas
- A4SWIFT, deploying schemas
- schemas, deploying
ms.assetid: a6aed2cd-3578-442e-ab1e-8284cc5f7b72
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc89b26d0eee970268d5e9084cd0827d3100fd7b
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25966424"
---
# <a name="deploying-a4swift-schemas"></a>A4SWIFT のスキーマを展開します。
交換する SWIFT メッセージのスキーマを展開する必要があります。  
  
 **概要**  
  
 次のスキーマを展開します。  
  
-   SWIFT Base Types.xsd  
  
-   SWIFT Common Data Types.xsd  
  
-   メッセージ型、MT103.xsd などの特定のスキーマ  
  
### <a name="to-create-a-strong-named-swift-project"></a>厳密な名前の SWIFT プロジェクトを作成するには  
  
1.  Visual Studio で、[**ファイル**、] をポイント**新規**、クリックして**プロジェクト**です。  
  
2.  新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**ペインで、 **BizTalk プロジェクト**フォルダーです。  
  
3.  **テンプレート**ペインで、**空の BizTalk Server プロジェクト**です。  
  
4.  **名前**ボックスで、プロジェクト名の名前を入力します。  
  
5.  **ソリューション**ボックスで、**新しいソリューションを作成**です。 **場所**ボックスに、スキーマにプロジェクトを追加するプロジェクトの場所を入力します。  
  
6.  をクリックして**OK**新しいプロジェクトを開きます。  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ソリューション エクスプ ローラーに新しいプロジェクトを追加し、指定されたフォルダーにプロジェクト フォルダーとファイルを作成します。  
  
7.  Visual Studio コマンド プロンプトを起動します。  
  
8.  Visual Studio コマンド プロンプトを参照 **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT**です。  
  
9. コマンド プロンプトで次のように入力します。 **sn – k key.snk**、ENTER キーを押します。 キーのペアが key.snk に書き込まれたことを示すコマンド プロンプト ウィンドウで、メッセージが表示されることを確認します。  
  
10. ソリューション エクスプ ローラーで、プロジェクト名を右クリックし、をクリックして**プロパティ**です。  
  
11. 左側のウィンドウで、**プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ**です。  
  
12. 右側のペインで、**プロパティ ページ**を下にスクロール ダイアログ ボックスで、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、をクリックし、省略記号ボタン () ボタンをクリックします。  
  
13. **アセンブリ キー ファイル** ダイアログ ボックスを参照 **\<*ドライブ*\>: \Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)]、クリックして**key.snk**、クリックして**開く**です。  
  
14. **プロパティ ページ**ダイアログ ボックスで、をクリックして**OK**変更を保存します。  
  
### <a name="to-add-a-swift-schema"></a>SWIFT スキーマに追加するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio でプロジェクトを開きます。  
  
2.  プロジェクトを右クリックし、順にポイント **追加**, 、クリックして **既存項目の**です。  
  
3.  **既存項目の追加** ダイアログ ボックスで、:\\**files \microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base スキーマ**です。 選択、 **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**スキーマ、およびクリック**追加**です。  
  
4.  プロジェクトを右クリックし、順にポイント**追加**、クリックして**既存項目の追加**です。  
  
5.  **既存項目の追加** ダイアログ ボックスで、**ファイルの場所**ドロップダウン ボックスに移動**\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT \<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Category n\MTxxx**です。 インスタンス メッセージの種類のスキーマを選択**MT103.xsd**、クリックして**追加**です。  
  
    > [!NOTE]
    >  ソリューション エクスプ ローラーで示すように、A4SWIFT は、プロジェクトのスキーマを追加します。  
  
6.  ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックし、 **ビルド**します。  
  
7.  ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックし、 **展開**します。