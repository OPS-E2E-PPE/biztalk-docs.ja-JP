---
title: Namespace コンポーネント サンプルを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f334a8-06de-4a56-a41a-3df088bf4a72
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83a24d2720fd9c46bd1d5ccb70d92a068f8a2ec4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021735"
---
# <a name="running-the-namespace-component-sample"></a>Namespace コンポーネント サンプルを実行します。
Namespace コンポーネントのサンプル アプリケーションを含む 4 つの場所/送信ポートのペアを受信します。 各ペアは、テストを表します。 以下は、4 つのテストです。  

- **パススルーに追加**します。 このテストでは、XML メッセージ ドキュメントに名前空間を追加し、新しい名前空間を表示することは、ファイルに直接メッセージを書き込みます。 このテストの入力ファイルでは、TEST_Add_to_PassThrough.0000.ns.xml です。 このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネント。  

- **削除する追加**します。 このテストでは、XML ドキュメントのメッセージに名前空間を追加しから削除します。 ファイルに直接メッセージを書き込みます。 このテストの入力ファイルでは、test _ Add_to_Remove.0000.ns.xml です。 このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネントと**NamespaceSampleSendPipeline** を格納している**RemoveNamespace**コンポーネント。  

- **削除するにはパススルー**します。 このテストでは、XML ドキュメントのメッセージからすべての名前空間を削除し、これを確認できるように、ファイルに直接、メッセージを書き込みます。 このテストの入力ファイルでは、TEST_PassThrough_to_Remove.0000.ns.xml です。 このテストでは、 **NamespaceSampleSendPipeline**を格納している、 **RemoveNamespace**コンポーネント。  

- **パススルーに抽出を使用して追加**します。 このテストの抽出、 **OrderDetails** XML の要素が、直接ファイルには、この要素を含む新しいメッセージをメッセージと書き込みをドキュメントします。 このテストの入力ファイルでは、TEST_AddViaExtraction_to_PassThrough.0000.ns.xml です。 このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネントを**ExtractionNodeXPath**プロパティに設定 **/CanonicalOrder/OrderDetails** (要素を返す任意の有効な XPath がこのプロパティで十分です)。  

  サンプル アプリケーションで基になる受信場所は、テストの種類ごとに該当するファイル マスクを持ち、受信ポート名での関連する送信ポート フィルター。 そのため、テストを実行するだけを削除する、適切に名前付きのメッセージを入力フォルダーに。 サンプル アプリケーションはテストを実行し、現在のテストでは、適切な名前を使用して、メッセージの ID を含む、出力フォルダーに更新されたメッセージをドロップします。  

  このセクションのトピックは次のとおりです。  

- [名前空間コンポーネント テストを実行する](../esb-toolkit/running-the-namespace-component-tests.md)  

- [名前空間の追加サンプルのしくみ](../esb-toolkit/how-the-add-namespace-sample-works.md)  

- [名前空間の削除サンプルのしくみ](../esb-toolkit/how-the-remove-namespace-sample-works.md)
