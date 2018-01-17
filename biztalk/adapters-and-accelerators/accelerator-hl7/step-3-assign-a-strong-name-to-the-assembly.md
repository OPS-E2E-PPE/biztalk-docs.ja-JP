---
title: "手順 3: アセンブリに厳密な名前を割り当てます |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies
- message enrichment tutorial, strong name assemblies
- strong name assemblies
ms.assetid: 8709e4e1-b428-42af-ba3c-08225c17a9eb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57368dbbb2d8ecaa6621707ea7b989bf7f5b005d
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="step-3-assign-a-strong-name-to-the-assembly"></a>手順 3: アセンブリに厳密な名前を割り当てます
この手順で作成して割り当てるの厳密な名前、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アセンブリ。 厳密な名前のアセンブリは、いくつかのセキュリティ上の利点を提供し、グローバル アセンブリ キャッシュ (GAC) でプロジェクトを展開するために必要な。 厳密な名前では、デジタル署名と一意キーのペアを割り当てることによって、アセンブリの一意性を保証します。 これは、アセンブリの系列をにより、それ以降のバージョンのアセンブリを生成できないことができますも保護します。 最後に、厳密な名前は、アセンブリの内容がのビルド以降に変更していないことを保証するために強力な整合性チェックを提供します。  
  
### <a name="to-assign-a-strong-name-to-the-assembly"></a>アセンブリに厳密な名前を割り当てる  
  
1.  開始 **Visual Studio コマンド プロンプト**します。  
  
    > [!NOTE]
    >  厳密な名前キーを既に作成した場合は、再利用することができます。  
  
2.  コマンド プロンプトでに移動**\<*ドライブ*\>: \Tutorial\BTAHL7V22Common** (ここで\<*ドライブ*\>はインストール ドライブ文字) キーを押します**Enter**です。  
  
3.  コマンド プロンプトで次のように入力します。 **sn – k key.snk**、キーを押します**Enter**です。 示すメッセージが表示されます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]キーファイル key.snk にキーのペアを書き込みました。  
  
4.  ソリューション エクスプ ローラーで右クリックし、 **BTAHL7V22Common**プロジェクトをクリックして**プロパティ**です。  
  
5.  BTAHL7V22Common プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**です。  
  
6.  右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンをクリックします。  
  
7.  アセンブリ キー ファイル ダイアログ ボックスでを参照 **\<*ドライブ*\>: \Tutorial\BTAHL7V22Common\key.snk**をクリックして**開く**、 をクリックし、**OK**です。  
  
8.  ソリューション エクスプ ローラーで右クリック**BTAHL7V22Common**、クリックして**展開**です。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]次のプロジェクトから参照できるアセンブリを作成します。  
  
9. BTAHL7V2XCommon プロジェクトに対して手順 4. ~ 8. を繰り返します。  
  
 進みます[手順 4: スキーマ作成](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)