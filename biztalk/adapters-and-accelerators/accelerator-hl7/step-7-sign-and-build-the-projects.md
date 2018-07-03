---
title: '手順 7: サインインし、プロジェクトのビルド |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, projects
- projects, building
- projects, signing
ms.assetid: b66e4dc1-4ec6-4ec0-a69a-419b116b19c1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b34ad40b7ee8e083f53e18c34e65fa3c8699d352
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970123"
---
# <a name="step-7-sign-and-build-the-projects"></a>手順 7: サインインし、プロジェクトのビルド
この手順で、厳密な名前を割り当てるし、で作成したリソース (スキーマ) を含むアセンブリを生成するプロジェクトをビルド[手順 6: スキーマの検証](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)です。 またこれにより、これまでに完了した作業でコンパイル エラーがないこと。  
  
### <a name="to-sign-the-btahl7-project"></a>BTAHL7 プロジェクトに署名するには  
  
1.  ソリューション エクスプ ローラーで右クリックして**BTAHL7 プロジェクト**、 をクリックし、**プロパティ**します。  
  
2.  BTAHL7 プロジェクト プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**します。  
  
3.  右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンを順にクリックします。  
  
4.  アセンブリ キー ファイル ダイアログ ボックスを参照 **\<*ドライブ*\>: \Tutorial\BTAHL7V22Common\key.snk** (で作成した[手順 3: に厳密な名前を割り当てる、アセンブリ](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md))、をクリックし、**オープン**します。  
  
5.  クリックして**OK**変更を保存します。  
  
### <a name="to-build-the-btahl7-project"></a>BTAHL7 プロジェクトをビルドするには  
  
- ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、 をクリックし、**デプロイ**します。 [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] DLL ファイルにアセンブリをコンパイルし、保存します、 \<*ドライブ*\>: \Tutorial\BTAHL7V22Common\Bin\Development フォルダー。  
  
  続行する[手順 8: BizTalk マッパーでマップの作成](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)