---
title: 'レッスン 2: SWIFTSchemas プロジェクト用の厳密な名前の BizTalk アセンブリを作成する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, creating strong-names
- strong-named assemblies
ms.assetid: 2aacbf38-8b1d-46ea-89ae-5207327bedc1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8e5b9ccc56b6b75ea574f956faac462e5b35dca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995523"
---
# <a name="lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project"></a>レッスン 2: SWIFTSchemas プロジェクト用の厳密な名前の BizTalk アセンブリを作成します。
このレッスンでは、BizTalk アセンブリをコンパイルおよび展開する、厳密な名前を作成します。 厳密な名前のアセンブリには、いくつかのセキュリティの利点があります。  
  
- 厳密な名前では、デジタル署名と一意キーのペアを割り当てることで、アセンブリの一意性を保証します。  
  
- 厳密な名前では、誰もそれ以降のバージョンのアセンブリを生成できることを確認して、アセンブリの系統を保護します。  
  
- 厳密な名前では、前回のビルド以降、アセンブリの内容が変更されていないことを保証するために厳密な整合性チェックを提供します。  
  
  付属する厳密な名前ツール (sn.exe) を使用してキー ファイルを生成できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]または[!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)]します。  
  
### <a name="to-create-a-strong-named-biztalk-assembly"></a>厳密な名前の BizTalk アセンブリを作成するには  
  
1. Visual Studio コマンド プロンプトを起動します。  
  
2. Visual Studio コマンド プロンプトを参照、 \<*ドライブ*\>: \labs フォルダー。  
  
3. コマンド プロンプトで「 **sn – k swift.snk**し、ENTER キーを押します。 成功メッセージが出力ウィンドウに表示されることを確認します。  
  
   > [!NOTE]
   >  適切なメッセージが表示されない場合は、Visual Studio を使用して、アセンブリのトラブルシューティングを行う。  
  
4. ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをクリックして**プロパティ**します。  
  
5. SWIFTSchemas プロパティ ページ] ダイアログ ボックスで、ことを確認します**共通プロパティ**は拡張、および [**アセンブリ**します。  
  
6. アセンブリのプロパティと右側のウィンドウで下にスクロール、**厳密な名前**セクションで、の右側に**アセンブリ キー ファイル**します。 省略記号ボタンをクリックします。  
  
7. アセンブリ キー ファイル ダイアログ ボックスを参照 **\<*ドライブ*:\>\labs**します。  
  
8. 選択、 **swift.snk**キーのファイルとしてファイルをクリックして**オープン**します。  
  
9. SWIFTSchemas プロパティ ページ] ダイアログ ボックスで、[ **OK**します。  
  
10. **ファイル** メニューのをクリックして**すべて保存**変更を保存します。  
  
    続行する[レッスン 3: SWIFT スキーマをプロジェクトに追加する](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md)します。