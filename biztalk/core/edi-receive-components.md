---
title: EDI の受信コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d3b82e8-1168-4c2c-bf1a-886b43ff8108
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5ffe09d7096e27111fc2db5cc2eff33b2d2713e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970075"
---
# <a name="edi-receive-components"></a>EDI の受信コンポーネント
このトピックでは、EDI/AS2 メッセージ以外の EDI メッセージを処理するパイプラインおよびパイプライン コンポーネントについて説明します。 受信した edi/as2 または非 edi/as2 メッセージの処理については、[AS2 の受信コンポーネント](../core/as2-receive-components.md)を参照してください。 AS2 の受信コンポーネントは、AS2 の処理だけではなく、EDI の処理も実行します。  
  
## <a name="edi-receive-pipeline"></a>EDI 受信パイプライン  
 EDI の受信処理は、EDI 受信パイプラインで実行されます。 このパイプラインは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] の Microsoft.BizTalk.Edi.EdiPipelines.dll にインストールされます。 このパイプラインは、任意のトランスポート経由で受信した EDI メッセージを処理します。 HTTP 経由で受信した AS2 でエンコードされた EDI メッセージは処理されません。 AS2 でエンコードされた EDI メッセージの処理は、AS2 パイプラインで実行されます。 AS2 受信パイプラインは、EDI メッセージの処理に EDI パイプラインと同じコンポーネントを使用します。  
  
> [!NOTE]
>  トランスポートの種類が HTTP であり、EDIReceive パイプラインを使用する受信場所を作成すると、セキュリティ上の問題が発生する可能性があります。 EdiReceive パイプラインでは、HTTP の "200 OK" 受信確認は生成されません。 EDI の受信確認が返されないと、接続が正常に終了せず、開いたままになります。 接続は、接続タイムアウト期間が経過したときにタイムアウトになります。  
  
 EDIReceive パイプラインは、次のパイプライン コンポーネントで構成されます。  
  
-   EDI 逆アセンブラー  
  
-   BatchMarker します。  
  
## <a name="edi-receive-pipeline-components"></a>EDI 受信パイプライン コンポーネント  
 EDIReceive パイプラインでは、次のパイプライン コンポーネントが使用されます。 これらのコンポーネントが microsoft.biztalk.edi.pipelinecomponents.dll にインストールされている[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]パイプライン コンポーネント\\します。  
  
### <a name="edi-disassembler"></a>EDI 逆アセンブラー  
 EDI 逆アセンブラーは、EDIReceive パイプラインにおいて、受信した EDI エンコード インターチェンジの処理の大部分を行います。 EDI 逆アセンブラーが EDI メッセージを処理する方法については、[、EDI 逆アセンブラーのしくみ](../core/how-the-edi-disassembler-works.md)を参照してください。  
  
### <a name="batchmarker"></a>BatchMarker  
 BatchMarker パイプライン コンポーネントは、バッチ化されたインターチェンジの処理に必要な BatchId、ToBeBatched、および ToBeRouted の各コンテキスト プロパティを昇格させることにより、インターチェンジをバッチ処理できるように準備します。 BatchMarker コンポーネントがこれらのプロパティを設定する方法は、バッチ要素をサブスクライブしている取引先アグリーメントの数によって決まります。  
  
- バッチ要素をサブスクライブしているアグリーメントが 1 つだけの場合、BatchMarker コンポーネントは ToBeBatched コンテキスト プロパティを True に設定して、バッチ処理オーケストレーションがバッチ要素を取得するようにします。  
  
- バッチ要素をサブスクライブしているアグリーメントが複数存在する場合、BatchMarker コンポーネントは ToBeRouted コンテキスト プロパティを True に設定して、ルーティング オーケストレーションがバッチ要素を取得するようにします。 また、BatchIds コンテキスト プロトコルを、バッチ ID のスペースで区切られた一覧に設定します。 ルーティング オーケストレーションは、各バッチ ID についてバッチ要素のコピーを 1 つ作成し、バッチ要素の各コピーの ToBeBatched プロパティを True に設定して、バッチ処理オーケストレーションがすべてのコピーを取得するようにします。  
  
  BatchMarker コンポーネントは、EDIReceive パイプラインの最後のステージ (取引先アグリーメントの解決) に含まれています。 EDI メッセージを処理するすべてのパイプラインに BatchMarker パイプライン コンポーネントが含まれている必要があります。  
  
> [!NOTE]
>  BatchMarker コンポーネントは、EDI メッセージを解析することなく取引先アグリーメントを解決するために、EDI 逆アセンブラーを含まない受信パイプラインに含めることができます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および BatchMarker コンポーネントを使用して、非 EDI メッセージをバッチ処理できます。 詳細については、の「処理非 EDI メッセージ BatchMarker コンポーネントでの」セクションを参照してください。[バッチ EDI インターチェンジをアセンブル](../core/assembling-a-batched-edi-interchange.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が EDI メッセージを受信する方法](../core/how-biztalk-server-receives-edi-messages.md)