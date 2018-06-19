---
title: '手順 7: 署名し、プロジェクトをビルド |Microsoft ドキュメント'
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
ms.openlocfilehash: f62a37da291bdc148369a28149cdfe29ed7fe446
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961768"
---
# <a name="step-7-sign-and-build-the-projects"></a>手順 7: 署名し、プロジェクトのビルド
この手順で、厳密な名前を割り当てるし、で作成したリソース (スキーマ) を含むアセンブリを生成するプロジェクトをビルド[手順 6: スキーマの検証](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)です。 またこれにより、これまでに完了した作業ではコンパイル エラーがないこと。  
  
### <a name="to-sign-the-btahl7-project"></a>BTAHL7 プロジェクトに署名するには  
  
1.  ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、クリックして**プロパティ**です。  
  
2.  BTAHL7 プロジェクト プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**です。  
  
3.  右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンをクリックします。  
  
4.  アセンブリ キー ファイル ダイアログ ボックスでを参照 **\<*ドライブ*\>: \Tutorial\BTAHL7V22Common\key.snk** (で作成されるよう[手順 3: に厳密な名前を割り当てる、アセンブリ](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md))、をクリックして**開く**です。  
  
5.  をクリックして**OK**変更を保存します。  
  
### <a name="to-build-the-btahl7-project"></a>BTAHL7 プロジェクトをビルドするには  
  
-   ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、クリックして**展開**です。 [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]DLL ファイルにアセンブリをコンパイルしで保存、 \<*ドライブ*\>: \Tutorial\BTAHL7V22Common\Bin\Development フォルダーです。  
  
 進みます[手順 8: BizTalk マッパーでマップの作成](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)