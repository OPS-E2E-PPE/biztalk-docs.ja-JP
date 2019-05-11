---
title: A4SWIFT スキーマの展開 |Microsoft Docs
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
ms.openlocfilehash: 3bcd4b739313affc65788b1511bed4bd786616c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378354"
---
# <a name="deploying-a4swift-schemas"></a>A4SWIFT スキーマの展開
交換する SWIFT メッセージのスキーマを展開する必要があります。  
  
 **まとめ**  
  
 次のスキーマを展開します。  
  
-   SWIFT Base Types.xsd  
  
-   SWIFT Common Data Types.xsd  
  
-   メッセージの種類では、たとえば、MT103.xsd に対して特定のスキーマ  
  
### <a name="to-create-a-strong-named-swift-project"></a>厳密な名前の SWIFT プロジェクトを作成するには  
  
1. Visual Studio で、次のようにクリックします。**ファイル**、 をポイント**新規**、 をクリックし、**プロジェクト**します。  
  
2. 新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**ペインで、 **BizTalk プロジェクト**フォルダー。  
  
3. **テンプレート**ペインで、**空の BizTalk Server プロジェクト**します。  
  
4. **名前**ボックスで、プロジェクト名の名前を入力します。  
  
5. **ソリューション**ボックスで、**新しいソリューションを作成**です。 **場所**ボックスに、スキーマ プロジェクトに追加するプロジェクトの場所を入力します。  
  
6. をクリックして**OK**を新しいプロジェクトを開きます。  
   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] ソリューション エクスプ ローラーに新しいプロジェクトを追加し、指定したフォルダーで、プロジェクト フォルダーとファイルを作成します。  
  
7. Visual Studio コマンド プロンプトを起動します。  
  
8. Visual Studio コマンド プロンプトを参照 **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT**します。  
  
9. コマンド プロンプトで「 **sn – k key.snk**し、ENTER キーを押します。 キーのペアが key.snk に書き込まれたことを示すコマンド プロンプト ウィンドウで、メッセージが表示されることを確認します。  
  
10. ソリューション エクスプ ローラーで、プロジェクト名を右クリックし をクリックし、**プロパティ**します。  
  
11. 左側のウィンドウで、**プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ**します。  
  
12. 右側のウィンドウで、**プロパティ ページ** ダイアログ ボックスで、下にスクロール、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、 をクリックし、省略記号 () ボタンをクリックします。  
  
13. **アセンブリ キー ファイル** ダイアログ ボックスを参照 **\<*ドライブ*\>: \Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)]、クリックして**key.snk**、クリックして**開く**です。  
  
14. **プロパティ ページ**ダイアログ ボックスで、をクリックして**OK**変更を保存します。  
  
### <a name="to-add-a-swift-schema"></a>SWIFT スキーマに追加するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio でプロジェクトを開きます。  
  
2.  プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。  
  
3.  **既存項目の追加** ダイアログ ボックスで、:\\**files \microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base スキーマ**します。 選択、 **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**スキーマ、およびクリック**追加**します。  
  
4.  プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の追加**します。  
  
5.  **既存項目の追加** ダイアログ ボックスで、**検索**ドロップダウン ボックスに移動**\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT \<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category n\MTxxx**します。 インスタンス メッセージの種類のスキーマを選択**MT103.xsd**、 をクリックし、**追加**します。  
  
    > [!NOTE]
    >  A4SWIFT は、ソリューション エクスプ ローラーで示すように、プロジェクトのスキーマを追加します。  
  
6.  ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**ビルド**します。  
  
7.  ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**デプロイ**します。