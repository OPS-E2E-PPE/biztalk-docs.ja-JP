---
title: 送信パイプライン |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, message flow
- send pipelines, about send pipelines
- messages, message flow
- send pipelines, stages
- pipelines, send pipelines
- messages, send pipelines
ms.assetid: c963b2d8-3b2b-4575-8105-c750deae8189
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef08909dbc47e11f5c9fecae6f65e01dbe79441b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270178"
---
# <a name="send-pipelines"></a>送信パイプライン
次の図は、メッセージ処理のワークフローです。送信パイプラインが強調表示されています。  
  
 ![メッセージを処理するためのワークフローのダイアグラム。] (../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")  
メッセージ処理ワークフロー  
  
 送信パイプラインでは、最終的な送信先に送られる前のドキュメントが処理されます。 送信パイプラインは、1 つのメッセージを取得し、送信する 1 つのメッセージを作成します。  
  
 新しい送信パイプラインを作成することも BizTalk Server に含まれる 2 つの既定の送信パイプラインのいずれかを使用することができます: パススルー送信パイプラインと XML 送信パイプラインです。  
  
 既定では、送信パイプラインは 3 つの空ステージで構成されます: プリアセンブル、アセンブル、およびエンコードします。 このトピックでは、これらのステージを設定する際に考慮すべき点について説明します。  
  
> [!NOTE]
>  使用するコンポーネントをパイプラインに追加すると、送信パイプラインは、ゼロ メッセージを作成できます。  
  
## <a name="pre-assemble-stage"></a>プリアセンブル ステージ  
  
-   このステージは、メッセージのシリアル化前にメッセージに対して処理を行うカスタム コンポーネントのプレースホルダーです。  
  
-   このステージは、メッセージごとに一度ずつ実行されます。  
  
-   このステージには、0 から 255 個までのコンポーネントを格納できます。  
  
-   この段階のすべてのコンポーネントが実行されます。  
  
## <a name="assemble-stage"></a>アセンブル ステージ  
  
-   このステージのコンポーネントは、メッセージのアセンブルまたはシリアル化を行い、XML への変換または XML からの変換を実行します。  
  
-   このステージには、0 または 1 個のコンポーネントを格納できます。  
  
-   この段階のすべてのコンポーネントが実行されます。  
  
## <a name="encode-stage"></a>エンコード ステージ  
  
-   このステージは、メッセージをエンコードまたは暗号化するコンポーネントに使用されます。  
  
    -   メッセージの署名が必要な場合は、このステージに MIME/SMIME エンコーダー コンポーネントまたはカスタム エンコード コンポーネントを配置します。  
  
-   このステージは、メッセージごとに一度ずつ実行されます。  
  
-   このステージには、0 から 255 個までのコンポーネントを格納できます。  
  
-   このステージのすべてのコンポーネントが実行されます。  
  
## <a name="see-also"></a>参照  
 [受信パイプライン](../core/receive-pipelines.md)   
 [パイプライン、ステージ、およびコンポーネントについて](../core/about-pipelines-stages-and-components.md)   
 [パイプラインの種類](../core/types-of-pipelines.md)   
 [既定のパイプライン](../core/default-pipelines.md)   
 [パイプライン テンプレート](../core/pipeline-templates.md)   
 [パイプライン コンポーネント](../core/pipeline-components.md)   
 [パイプライン コンポーネントの種類](../core/types-of-pipeline-components.md)