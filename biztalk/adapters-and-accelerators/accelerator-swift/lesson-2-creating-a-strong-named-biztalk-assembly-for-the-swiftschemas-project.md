---
title: "レッスン 2: SWIFTSchemas プロジェクト用の厳密な名前の BizTalk アセンブリの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies, creating strong-names
- strong-named assemblies
ms.assetid: 2aacbf38-8b1d-46ea-89ae-5207327bedc1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8ff979c7b6915f53ebc7144cf0774ab1ffb779a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project"></a>レッスン 2: SWIFTSchemas プロジェクト用の厳密な名前の BizTalk アセンブリを作成します。
このレッスンでは、BizTalk アセンブリのコンパイルし、展開の基になる、厳密な名前を作成します。 厳密な名前のアセンブリには、いくつかのセキュリティの利点があります。  
  
-   厳密な名前では、デジタル署名と一意キーのペアを割り当てることによって、アセンブリの一意性を保証します。  
  
-   厳密な名前では、それ以降のバージョンのアセンブリを生成できます誰もできるようにして、アセンブリの系列を保護します。  
  
-   厳密な名前では、アセンブリの内容が前回のビルド以降変更されていないことを保証するために強力な整合性チェックを提供します。  
  
 付属している厳密名ツール (sn.exe) を使用してキー ファイルを生成することができます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]または[!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)]です。  
  
### <a name="to-create-a-strong-named-biztalk-assembly"></a>厳密な名前の BizTalk アセンブリを作成するには  
  
1.  Visual Studio コマンド プロンプトを起動します。  
  
2.  Visual Studio コマンド プロンプトを参照、 \<*ドライブ*\>: \labs フォルダーです。  
  
3.  コマンド プロンプトで次のように入力します。 **sn – k swift.snk**、ENTER キーを押します。 成功メッセージが出力ウィンドウに表示されることを確認します。  
  
    > [!NOTE]
    >  適切なメッセージが表示されない場合は、Visual Studio を使用して、アセンブリのトラブルシューティングを行います。  
  
4.  ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをクリックして**プロパティ**です。  
  
5.  SWIFTSchemas プロパティ ページ] ダイアログ ボックスで、いることを確認**共通プロパティ**が拡張され、[**アセンブリ**です。  
  
6.  アセンブリのプロパティと右側のペインで下へスクロールして、**厳密な名前**セクションで、の右側に**アセンブリ キー ファイル**です。 省略記号ボタンをクリックします。  
  
7.  アセンブリ キー ファイル ダイアログ ボックスでを参照  **\<*ドライブ*:\>\labs** です。  
  
8.  選択、 **swift.snk**クリックしてファイルをキー ファイルとして**開く**です。  
  
9. SWIFTSchemas プロパティ ページ] ダイアログ ボックスで、[ **OK**です。  
  
10. **ファイル** メニューのをクリックして**すべて保存**して変更を保存します。  
  
 進みます[レッスン 3: SWIFT スキーマをプロジェクトに追加する](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md)です。