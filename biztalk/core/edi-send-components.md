---
title: EDI 送信コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce270db-a573-48b3-be15-0178a5b7785b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9afcc401b800fab7b549ac9bc4c53ae7502b8caa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350272"
---
# <a name="edi-send-components"></a>EDI 送信コンポーネント
このトピックでは、EDI/AS2 メッセージ以外の EDI メッセージを処理するパイプラインおよびパイプライン コンポーネントについて説明します。 EDI および AS2 または EDI および AS2 メッセージの送信方法の詳細については、次を参照してください。 [AS2 送信コンポーネント](../core/as2-send-components.md)します。 AS2 送信コンポーネントが EDI AS2 の処理だけでなく処理を実行することに注意してください。  
  
## <a name="edi-send-pipeline"></a>EDI 送信パイプライン  
 EDI 送信処理は、次の EDISend パイプラインで実行されます。 このパイプラインがインストールされている`Microsoft.BizTalk.Edi.EdiPipelines.dll`で[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]します。  
  
 **EDISend パイプライン**  
  
 このパイプラインは、生成し、EDI メッセージを送信します。 HTTP 経由で受信した AS2 でエンコードされた EDI メッセージは処理されません。 AS2 でエンコードされた EDI メッセージの処理は、AS2 パイプラインによって実行されます。 AS2 送信パイプラインに EDI パイプラインと EDI メッセージを処理するのにのと同じコンポーネントを使用します。  
  
> [!NOTE]
>  オーケストレーションからの EDISend パイプラインの実行はサポートされていません。  
  
> [!NOTE]
>  AS2EDISend パイプラインでは、生成し、AS2 トランスポート経由で EDI メッセージを送信します。 詳細については、次を参照してください。 [AS2 送信コンポーネント](../core/as2-send-components.md)します。  
  
 パイプラインは、EDI アセンブラー パイプライン コンポーネントで構成されます。  
  
## <a name="edi-send-pipeline-component"></a>EDI 送信パイプライン コンポーネント  
 EDISend パイプラインは、EDI アセンブラー パイプライン コンポーネントを使用します。 このコンポーネントがインストールされている`Microsoft.BizTalk.Edi.PipelineComponents.dll`で[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]パイプライン コンポーネント\\します。  
  
 EDI アセンブラーは、EDISend パイプラインで EDI エンコード インターチェンジの処理の大部分を実行します。 EDI アセンブラーが EDI メッセージを処理する方法については、次を参照してください。 [、EDI アセンブラーのしくみ](../core/how-the-edi-assembler-works.md)します。