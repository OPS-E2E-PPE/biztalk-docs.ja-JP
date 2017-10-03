---
title: "Namespace コンポーネント サンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f334a8-06de-4a56-a41a-3df088bf4a72
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fc142ca70971f023e491dbdeee693a8d41c42fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-namespace-component-sample"></a>Namespace コンポーネント サンプルを実行します。
Namespace コンポーネント サンプル アプリケーションを含む 4 つの場所/送信ポートのペアを受信します。 各ペアは、テストを表します。 4 つのテストを次に示します。  
  
-   **パススルーに追加**です。 このテストでは、XML メッセージ ドキュメントに名前空間を追加し、新しい名前空間を認識できるように、ファイルに直接メッセージを書き込みます。 このテストの入力ファイルでは、TEST_Add_to_PassThrough.0000.ns.xml です。 このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネントです。  
  
-   **削除する追加**です。 このテストでは、XML ドキュメントのメッセージに名前空間を追加、削除されます。 これは、後、ファイルに直接メッセージを書き込みます。 このテストの入力ファイルでは、test _ Add_to_Remove.0000.ns.xml です。 このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネントおよび**NamespaceSampleSendPipeline**を含む、 **RemoveNamespace**コンポーネントです。  
  
-   **削除するにはパススルー**です。 このテストでは、XML ドキュメントのメッセージからすべての名前空間を削除しが確認できるように、ファイルに直接メッセージを書き込みます。 このテストの入力ファイルでは、TEST_PassThrough_to_Remove.0000.ns.xml です。 このテストでは、 **NamespaceSampleSendPipeline**を格納している、 **RemoveNamespace**コンポーネントです。  
  
-   **抽出パススルーを使用して追加**です。 このテストの抽出、 **OrderDetails** XML の要素と文書化メッセージの書き込み、ファイルに直接には、この要素を含む新しいメッセージ。 このテストの入力ファイルでは、TEST_AddViaExtraction_to_PassThrough.0000.ns.xml です。 このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネントを**ExtractionNodeXPath**プロパティに設定**/CanonicalOrder/OrderDetails** (要素を返す任意の有効な XPath がこのプロパティには十分)。  
  
 サンプル アプリケーションで基になる受信場所はテストの種類ごとに該当するファイル マスクを持ち、関連する送信ポート フィルターを受信ポートの名前。 そのため、テストを実行するだけにドロップする適切に名前付きのメッセージ入力フォルダーです。 サンプル アプリケーションのテストを実行し、現在のテストでは、適切な名前を使用して、メッセージの ID を含む出力フォルダーに、更新されたメッセージをドロップ  
  
 このセクションのトピックは次のとおりです。  
  
-   [Namespace コンポーネントのテストを実行しています。](../esb-toolkit/running-the-namespace-component-tests.md)  
  
-   [どのように Namespace サンプルは、動作を追加](../esb-toolkit/how-the-add-namespace-sample-works.md)  
  
-   [削除 Namespace サンプルのしくみ](../esb-toolkit/how-the-remove-namespace-sample-works.md)