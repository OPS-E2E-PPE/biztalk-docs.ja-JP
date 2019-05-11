---
title: BizTalk Server プロジェクトでの単体テスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2594f29-fc34-4dda-9316-2afd4e0056d7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19cb904341baf5d6a48af2ea55006522793b3d59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292633"
---
# <a name="unit-testing-with-biztalk-server-projects"></a>BizTalk Server プロジェクトでの単体テスト
BizTalk Server には、単体テストを有効にできる機能が導入された、**展開**BizTalk プロジェクトのプロパティ ページ。 次のスクリーン ショットは、このプロジェクトのプロジェクトを右クリックすると、プロジェクト デザイナーからアクセス設定を示しています、**プロパティ**します。  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **プロジェクトの単体テストを有効にするプロパティを公開するプロジェクト デザイナーの [展開] タブのスクリーン ショット。**  
  
 この機能は、スキーマ、マップ、用の単体テストを作成することができ、パイプラインします。 このセクションのトピックでは、単体テスト機能を使用するアプローチの例をいくつかを説明します。 この機能が有効になっているし、プロジェクトを再構築、成果物の単体テストをサポートするために次の基本クラスからクラスが派生されます。  
  
|成果物の種類|基本クラス|  
|-------------------|----------------|  
|スキーマ|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|マップ|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|パイプライン|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [単体テストのスキーマとマップを含む機能を使用します。](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)  
  
-   [単体テストのパイプラインを持つ機能を使用します。](../core/using-the-unit-testing-feature-with-pipelines.md)  
  
## <a name="related-sections"></a>関連項目  
 [単体テスト (Visual Studio) の操作](http://go.microsoft.com/fwlink/?LinkId=128890)