---
title: "EDI 送信コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fce270db-a573-48b3-be15-0178a5b7785b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5520a0c1dd0a6ef7e42818314a9f87733aebcb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-send-components"></a>EDI 送信コンポーネント
このトピックでは、EDI/AS2 メッセージ以外の EDI メッセージを処理するパイプラインおよびパイプライン コンポーネントについて説明します。 EDI および AS2 の EDI および AS2 メッセージを送信する方法については、次を参照してください。 [AS2 送信コンポーネント](../core/as2-send-components.md)です。 AS2 の送信コンポーネントは、AS2 の処理だけでなく、EDI の処理も実行します。  
  
## <a name="edi-send-pipeline"></a>EDI 送信パイプライン  
 EDI 送信処理は、次の EDISend パイプラインで実行されます。 このパイプラインは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] の `Microsoft.BizTalk.Edi.EdiPipelines.dll` にインストールされます。  
  
 **EDISend パイプライン**  
  
 このパイプラインでは、EDI メッセージを生成し、送信します。 HTTP 経由で受信した AS2 でエンコードされた EDI メッセージは処理されません。 AS2 でエンコードされた EDI メッセージの処理は、AS2 パイプラインで実行されます。 AS2 送信パイプラインでは、EDI メッセージの処理に EDI パイプラインと同じコンポーネントを使用します。  
  
> [!NOTE]
>  オーケストレーションからの EDISend パイプラインの実行はサポートされていません。  
  
> [!NOTE]
>  AS2EDISend パイプラインでは、EDI メッセージを生成し、AS2 トランスポート経由で送信します。 詳細については、次を参照してください。 [AS2 送信コンポーネント](../core/as2-send-components.md)です。  
  
 このパイプラインは、EDI アセンブラー パイプライン コンポーネントで構成されます。  
  
## <a name="edi-send-pipeline-component"></a>EDI 送信パイプラインのコンポーネント  
 EDISend パイプラインでは、EDI アセンブラー パイプライン コンポーネントが使用されます。 このコンポーネントがインストールされている`Microsoft.BizTalk.Edi.PipelineComponents.dll`で[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]パイプライン コンポーネント\\です。  
  
 EDI アセンブラーは、EDISend パイプラインにおいて、EDI エンコード インターチェンジの処理の大部分を担当します。 EDI アセンブラーが EDI メッセージを処理する方法については、次を参照してください。 [「EDI アセンブラーの動作](../core/how-the-edi-assembler-works.md)です。