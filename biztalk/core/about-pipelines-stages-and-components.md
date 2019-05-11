---
title: パイプライン、ステージ、およびコンポーネントについて |Microsoft Docs
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
ms.openlocfilehash: 04bef6e1c443ca2723029014f5a4d3b703b4d7a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362349"
---
# <a name="about-pipelines-stages-and-components"></a>パイプライン、ステージ、およびコンポーネントについて
パイプラインは、定義済みの順序でメッセージを処理する .NET または COM コンポーネントのセットを含むソフトウェア インフラストラクチャです。 パイプラインは、処理ステージと呼ばれる作業のカテゴリを除算し、ステージが実行されるシーケンスを決定します。 各ステージは、作業の論理グループを定義、段階に移動したり、コンポーネントを決定およびステージにおけるパイプライン コンポーネントを実行する方法を指定します。  
  
 各ステージでは、内では、パイプライン コンポーネントは、特定のタスクを実行します。 たとえば、受信パイプラインのステージ内のコンポーネントがデコード、逆アセンブルし、他の形式からドキュメントを XML に変換します。 送信パイプラインは基本的に逆: ドキュメントを XML から他の形式に変換、アセンブル、およびプロセス全体の一部を実行する各パイプライン コンポーネントを暗号化します。 ステージには、コンポーネントのコンテナーが、各ステージ自体がメタデータを持つコンポーネントです。 ステージは、実行コードを持つパイプライン コンポーネントではなく、実行コードを持つありません。  
  
 次の図は、パイプラインのデザイン画面がパイプラインに示しています。 このパイプラインには、2 つの段階、アセンブル ステージとエンコード段階があります。 XML アセンブラー パイプライン コンポーネントがアセンブル ステージに追加されましたが、表示されたままにするため、エンコード ステージが空のまま、**ここにドロップします。** パイプライン コンポーネントをステージに追加できることを示します。  
  
 ![BizTalk パイプラインのステージおよびコンポーネント](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")  
BizTalk パイプラインのステージおよびコンポーネントを示しています。  
  
 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パイプライン テンプレート、パイプライン コンポーネント、および既定のパイプラインのセットが含まれています。 作成して、パイプライン デザイナー ユーザー インターフェイスを使用してパイプラインを構成します。API を使用してパイプラインを実装する、 **Microsoft.BizTalk.Component.Interop**名前空間。 パイプライン テンプレートを変更することはできません。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パイプラインの種類](../core/types-of-pipelines.md)  
  
-   [パイプライン コンポーネントの種類](../core/types-of-pipeline-components.md)  
  
-   [パイプラインのステージ](../core/pipeline-stages.md)  
  
-   [既定のパイプライン](../core/default-pipelines.md)  
  
-   [パイプラインのテンプレート](../core/pipeline-templates.md)  
  
-   [パイプライン コンポーネント](../core/pipeline-components.md)  
  
-   [パイプライン コンポーネントのスキーマ解決](../core/schema-resolution-in-pipeline-components.md)  
  
-   [XML アセンブラーおよび逆アセンブラー パイプライン コンポーネントでのエンベロープの使用](../core/envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components.md)  
  
-   [アセンブラー パイプライン コンポーネントでのプロパティの降格](../core/property-demotion-in-assembler-pipeline-components.md)  
  
-   [逆アセンブラー パイプライン コンポーネントでのプロパティの昇格](../core/property-promotion-in-disassembler-pipeline-components.md)  
  
-   [逆アセンブラー パイプライン コンポーネントでの識別フィールド](../core/distinguished-fields-in-disassembler-pipeline-components.md)