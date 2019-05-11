---
title: 単体テスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c40e5b82-dbb2-4767-8286-88e2de4129f3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d92743dbfde629212231e9fb8a1e73496f4ca6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400595"
---
# <a name="unit-testing"></a>単体テスト
BizTalk Server に単体テストで有効にする機能が導入されています、**展開**BizTalk プロジェクトのプロパティ ページ。 次のスクリーン ショットは、このプロジェクトのプロジェクトを右クリックすると、プロジェクト デザイナーからアクセス設定を示しています。**プロパティ**します。  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **プロジェクトの単体テストを有効にするプロパティを公開するプロジェクト デザイナーの [展開] タブのスクリーン ショット**  
  
 この機能は、スキーマ、マップ、用の単体テストを作成することができ、パイプラインします。 BizTalk Server のドキュメントでは、単体テスト機能を使用するアプローチの例をいくつか説明します。 この機能が有効になっているし、プロジェクトを再構築、成果物の単体テストをサポートするために次の基本クラスからクラスが派生されます。  
  
|成果物の種類|基本クラス|  
|-------------------|----------------|  
|スキーマ|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|マップ|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|パイプライン|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
 単体テストの BizTalk Server で導入された機能の詳細については、BizTalk Server ヘルプで、次のトピックを参照してください。  
  
-   [単体テストのスキーマとマップを含む機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150482)(http://go.microsoft.com/fwlink/?LinkId=150482)します。  
  
-   [単体テストのパイプラインを持つ機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150483)(http://go.microsoft.com/fwlink/?LinkId=150483)  
  
## <a name="see-also"></a>参照  
 [自動テストの実装](../technical-guides/implementing-automated-testing.md)