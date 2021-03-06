---
title: パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines
- deploying, pipelines
- receive pipelines, about receive pipelines
- pipelines, deploying
- send pipelines, about send pipelines
- receive pipelines
- pipelines, about pipelines
- send pipelines, stages
- send pipelines
- pipelines, receive pipelines
- pipelines, send pipelines
- receive pipelines, stages
ms.assetid: 76947dd8-728a-4fa3-bd33-7a708ae82cac
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8ef3fab99e8356d00da859a29548064fc4af086
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395744"
---
# <a name="pipelines"></a>パイプライン
パイプラインは、パイプとフィルターの統合パターンの実装を提供する Microsoft BizTalk Server のコンポーネントです。 受信およびメッセージの送信中には、ビジネス上の理由を入力または BizTalk Server を準備するためにメッセージの変換を実行します。  
  
 一般的な例は、活用するために特定の機能では、BizTalk Server マップ; など、コンマで区切られたフラット ファイルを XML ファイルに変換する必要があります。フラット ファイル逆アセンブラー コンポーネントを実行します。 受信または送信する前にいくつかの種類のメッセージに変換を実行する必要がある統合シナリオでは一般的パイプラインは、この要件を満たすために使用されます。 パイプラインを使用する一連のされるように、メッセージに対して実行される変換を定義する開発者の受信または送信します。  
  
 これらが実行されるポートを一致と 2 つの種類のパイプライン、送信および受信するがあります。 *送信パイプライン*は送信ポートで実行され、要求/応答の応答部分では、受信ポート、中に*受信パイプライン*実行では、受信場所、および送信請求-応答の応答部分で送信ポート。 基本的に、受信パイプラインは、送信パイプラインにサブスクライブしているし、BizTalk Server から送信されるメッセージで使用するものでは、メッセージ ボックス データベースに公開されるメッセージの変換に使用されます。  
  
 各パイプラインには、パイプラインが実行されるときの順序で実行されるステージのセットがあります。 各ステージは、0 個以上のコンポーネントを含めることができます。 コンポーネントの最大数はステージによって異なります。  
  
## <a name="receive-pipeline-stages"></a>受信パイプラインのステージ  
 ![受信パイプラインのステージ](../core/media/arch-pipe-receive.gif "arch_pipe_receive")  
  
|ステージ|目的|  
|-----------|-------------|  
|**デコード**|復号化、またはメッセージ データをデコードします。|  
|**逆アセンブルします。**|小さいメッセージにインターチェンジを逆アセンブルし、メッセージの内容を解析します。|  
|**[検証]**|一般に、スキーマに対して、メッセージ データを検証します。|  
|**パーティを解決します。**|メッセージまたはメッセージのコンテキストでは、いくつかのセキュリティ トークンに関連付けられた BizTalk Server パーティを識別します。|  
  
## <a name="send-pipeline-stages"></a>送信パイプラインのステージ  
 ![送信パイプラインのステージ](../core/media/arch-pipe-send.gif "arch_pipe_send")  
  
|ステージ|目的|  
|-----------|-------------|  
|**プリアセンブルします。**|すべてのメッセージ、メッセージをアセンブルする前に必要な処理を実行します。|  
|**アセンブル**|メッセージをアセンブルし、送信される XML に変換するフラット ファイル、またはその他のタスクは、受信パイプラインの逆アセンブル ステージを補完、エンベロープの追加などの手順を実行できるように準備します|  
|**エンコード**|配信する前にメッセージを暗号化またはエンコードします。|  
  
 パイプラインのステージが、*実行モード*すべてまたは First Match ステージに 1 つ以上のコンポーネントが追加された場合に実行するコンポーネントを制御します。 ステージのすべてのモードでは、ステージで構成されている順序でメッセージを処理する各コンポーネントが呼び出されます。 最初の一致のモードの場合は、各コンポーネントをポーリングして、この時点で一致するコンポーネントが実行されて、残りのコンポーネントは実行されません、一致が見つかるまで、正しいコンポーネントことを示します。  
  
 実行モードの例として、受信パイプラインの逆アセンブル ステージが First Match ステージには、ステージ内の各コンポーネントがメッセージを認識し、処理できるかどうかに表示すると呼ばれるためです。 コンポーネントは、肯定で応答する場合、そのステージの他のコンポーネントなしにたずねますメッセージを処理できるかどうかを参照してください。 ただし、受信パイプラインのデコード ステージには、このステージでは、各コンポーネントが呼び出され、構成された順序でメッセージを処理することを意味する、すべての実行モードがあります。 最初のデコーダーは、中、2 つ目は、zip 形式からメッセージを圧縮解除を行う可能性があります、メッセージを復号化する可能性があります。  
  
 パイプライン処理の実行モードの 1 つの一般的な結果には、開発者が 1 つの受信パイプラインで複数の逆アセンブラーを使用する場合に発生します。 2 つのファイルの逆アセンブラーと似ていますが、別のスキーマが構成されているフラットなどは、多くの場合、逆アセンブラー コンポーネントはわずかに異なります。 この場合、メッセージでは、2 番目の逆アセンブラーで定義されたスキーマが実際に一致、中には、最初の逆アセンブラーがメッセージを処理できるとプローブで判断可能性があります。 エラーが検出されるメッセージと中断メッセージを処理した後のみになります。 このような場合は、いずれかを具体的なプローブ ロジックを持つ新しい逆アセンブラーを作成または 2 つの異なるパイプラインを作成して受信できます、さまざまな異なる内のメッセージの受信場所。  
  
## <a name="pipeline-deployment"></a>パイプラインの展開  
 パイプラインを含むアセンブリを展開するときに、パイプラインが、管理データベースに保存します。 パイプラインは、次の結果でアセンブリの特定のバージョンに関連付けられています。  
  
-   同じパイプラインを使用する複数のアセンブリを展開する場合、管理データベースは、各アセンブリのパイプラインの 1 つのエントリを作成します。  
  
-   パイプラインを含むアセンブリを削除するときに、管理データベースは、アセンブリに関連付けられているパイプラインを削除します。 管理データベースに関連付けられている各アセンブリのパイプラインのコピーがあるため、1 つのアセンブリを削除するには影響しません、他のユーザー。  
  
## <a name="see-also"></a>参照  
 [アイテム](../core/artifacts.md)