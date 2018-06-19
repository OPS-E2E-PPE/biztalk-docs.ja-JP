---
title: パイプライン、ステージ、およびコンポーネントについて |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Microsoft.BizTalk.Component.Interop namespace
- pipelines, about pipelines
ms.assetid: a98e1c93-f264-4577-bd12-4430a5859e3c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 070c785924021f8e398a547c01afe969fa6430cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225466"
---
# <a name="about-pipelines-stages-and-components"></a>パイプライン、ステージ、およびコンポーネントについて
パイプラインとは、事前に定義された順序でメッセージを処理する、一連の .NET コンポーネントまたは COM コンポーネントを含んだソフトウェア インフラストラクチャのことです。 パイプラインでは、処理がステージと呼ばれる作業単位に分割されます。各ステージの順序もパイプラインによって決定されます。 ステージごとに論理的なワークグループが定義され、使用コンポーネントが決定されるほか、そのステージにおけるパイプライン コンポーネントの実行方法も指定されます。  
  
 各ステージでは、それぞれのパイプライン コンポーネントが固有のタスクを実行します。 たとえば、受信パイプラインのステージに含まれるコンポーネントは、デコード、逆アセンブル、変換などの各タスクを通じて、特定の形式のドキュメントを XML 形式に変換します。 送信パイプラインは、逆に、基本的には: ドキュメントを XML から他の形式に変換する、アセンブル、および暗号化には、プロセス全体の一部を実行する各パイプライン コンポーネントを使用します。 ステージはコンポーネントのコンテナーであると共に、各ステージはそれ自体がメタデータを持つコンポーネントといえます。 実行コードを持つパイプライン コンポーネントとは異なり、ステージには実行コードがありません。  
  
 次の図は、パイプライン デザイン画面でパイプラインがどのように表されるかを示しています。 このパイプラインには、アセンブル ステージとエンコード ステージという 2 つのステージがあります。 XML アセンブラー パイプライン コンポーネントがアセンブル ステージに追加されましたが、エンコード ステージでは、空のまま表示されたままに**ここにドロップします。** これは、ステージが空であること、つまりパイプライン コンポーネントを追加できることを示しています。  
  
 ![BizTalk パイプラインのステージおよびコンポーネント](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")  
BizTalk パイプラインのステージおよびコンポーネントを示します。  
  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、パイプライン テンプレート、パイプライン コンポーネント、および既定のパイプラインが複数用意されています。 作成して、パイプライン デザイナー ユーザー インターフェイスを使用してパイプラインを構成します。内の API を使用してパイプラインを実装する、 **Microsoft.BizTalk.Component.Interop**名前空間。 パイプライン テンプレートを変更することはできません。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パイプラインの種類](../core/types-of-pipelines.md)  
  
-   [パイプライン コンポーネントの種類](../core/types-of-pipeline-components.md)  
  
-   [パイプライン ステージ](../core/pipeline-stages.md)  
  
-   [既定のパイプライン](../core/default-pipelines.md)  
  
-   [パイプライン テンプレート](../core/pipeline-templates.md)  
  
-   [パイプライン コンポーネント](../core/pipeline-components.md)  
  
-   [スキーマの解決パイプライン コンポーネント](../core/schema-resolution-in-pipeline-components.md)  
  
-   [XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用](../core/envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components.md)  
  
-   [アセンブラー パイプライン コンポーネントでプロパティの降格](../core/property-demotion-in-assembler-pipeline-components.md)  
  
-   [逆アセンブラー パイプライン コンポーネントのプロパティの昇格](../core/property-promotion-in-disassembler-pipeline-components.md)  
  
-   [識別フィールドに逆アセンブラー パイプライン コンポーネント](../core/distinguished-fields-in-disassembler-pipeline-components.md)