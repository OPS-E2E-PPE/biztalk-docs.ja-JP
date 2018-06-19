---
title: 単体テスト |Microsoft ドキュメント
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
ms.openlocfilehash: d5f792adf73fb1e3791f0dfe6c8c5f60a3bb81e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009835"
---
# <a name="unit-testing"></a>単体テスト
BizTalk Server には、単体テストを有効にできる機能が導入されています、**展開**BizTalk プロジェクトのプロパティ ページ。 次のスクリーン ショットは、このプロジェクトのプロジェクトを右クリックすると、プロジェクト デザイナーからアクセス設定を示しています。**プロパティ**です。  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **単体テスト プロジェクトのプロパティを公開するプロジェクト デザイナーの 展開 タブのスクリーン ショット**  
  
 この機能により、スキーマ、マップ、パイプラインの単体テストを作成できます。 BizTalk Server のドキュメントのトピックでは、単体テスト機能を使用するアプローチの例をいくつかを説明します。 この機能を有効にしてプロジェクトを再構築すると、次の基本クラスから、単体テストをサポートするためのアイテム クラスが派生します。  
  
|アイテムの種類|基本クラス|  
|-------------------|----------------|  
|スキーマ|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|マップ|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|パイプライン|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
 単体テストで BizTalk Server で導入された機能の詳細については、BizTalk Server ヘルプの次のトピックを参照してください。  
  
-   [単体テストのスキーマおよびマップの機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150482)(http://go.microsoft.com/fwlink/?LinkId=150482)。  
  
-   [単体テストでのパイプライン機能を使用して](http://go.microsoft.com/fwlink/?LinkId=150483)(http://go.microsoft.com/fwlink/?LinkId=150483)  
  
## <a name="see-also"></a>参照  
 [自動テストの実装](../technical-guides/implementing-automated-testing.md)