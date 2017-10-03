---
title: "単体テスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c40e5b82-dbb2-4767-8286-88e2de4129f3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa6dd215aee23f49442e614649fa33f7321d42e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unit-testing"></a>単体テスト
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]単体テストで有効にする機能が導入されています、**展開**BizTalk プロジェクトのプロパティ ページ。 次のスクリーン ショットは、このプロジェクトのプロジェクトを右クリックすると、プロジェクト デザイナーからアクセス設定を示しています。**プロパティ**です。  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **単体テスト プロジェクトのプロパティを公開するプロジェクト デザイナーの 展開 タブのスクリーン ショット**  
  
 この機能により、スキーマ、マップ、パイプラインの単体テストを作成できます。 各トピックで、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ドキュメントは、単体テスト機能を使用する、いくつかのアプローチの例を提供します。 この機能を有効にしてプロジェクトを再構築すると、次の基本クラスから、単体テストをサポートするためのアイテム クラスが派生します。  
  
|アイテムの種類|基本クラス|  
|-------------------|----------------|  
|スキーマ|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|マップ|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|パイプライン|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
 詳細については、単体テスト機能で導入された[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]、次のトピックを参照してください、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。  
  
-   [単体テストのスキーマおよびマップの機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150482)(http://go.microsoft.com/fwlink/?LinkId=150482)。  
  
-   [単体テストでのパイプライン機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150483)(http://go.microsoft.com/fwlink/?LinkId=150483)  
  
## <a name="see-also"></a>参照  
 [テストの自動化を実装します。](../technical-guides/implementing-automated-testing.md)