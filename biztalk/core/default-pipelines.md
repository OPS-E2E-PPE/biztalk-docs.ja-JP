---
title: "既定のパイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, PassThruTransmit
- pipelines, PassThruReceive
- pipelines, XMLTransmit
- pipelines, StsReceive
- pipelines, StsSend
- pipelines, StsFileReceive
- Microsoft.BizTalk.KwTpm.StsDefaultPipelines.EnvSchema XML envelope
- pipelines, XMLReceive
- pipelines, backward compatibility
- Microsoft.BizTalk.DefaultPipelines assembly
- pipelines, default
ms.assetid: 7d82bb2c-c7f1-44a1-9e1b-89b0bb806845
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ceb3f06f2e2b57ec37bc4a95a385574de594940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="default-pipelines"></a>既定のパイプライン
新しいアプリケーションを作成すると、既定のパイプラインが作成および展開され、各 BizTalk プロジェクトに対して、\References フォルダーの Microsoft.BizTalk.DefaultPipelines アセンブリに表示されます。 パイプライン デザイナーでは、既定のパイプラインを変更できません。 これらのパイプラインは、送信ポートまたは受信場所を BizTalk エクスプローラーで構成するときに選択できます。 ここでは、既定のパイプラインの概要および使用時期について説明します。  
  
> [!NOTE]
>  XML 受信パイプラインおよび送信パイプラインは、4 GB を超える XML ドキュメントをサポートしません。  
  
## <a name="passthrureceive-pipeline"></a>PassThruReceive パイプライン  
 パススルー受信パイプラインはコンポーネントを持っていません。 このパイプラインは、メッセージ ペイロード処理を必要としないシンプル パススルー シナリオに使用されます。 一般に、メッセージの送信元と送信先が既知であり、メッセージが検証、エンコーディング、または逆アセンブルを必要としない場合に使用されます。 通常は、パススルー送信パイプラインと一緒に使用されます。  
  
 パススルー受信パイプラインには逆アセンブラーが含まれていないので、メッセージのオーケストレーションへのルーティングに使用できません。  
  
> [!NOTE]
>  パススルー受信パイプラインは、プロパティの昇格をサポートしていません。  
  
## <a name="passthrutransmit-pipeline"></a>PassThruTransmit パイプライン  
 パススルー送信パイプラインはコンポーネントを持っていません。 このパイプラインは、一般に、メッセージを送信先に送信する前のドキュメント処理を必要としない場合に使用されます。  
  
## <a name="xmlreceive-pipeline"></a>XMLReceive パイプライン  
 XML 受信パイプラインは、次のステージで構成されます。  
  
-   **デコードします。** 空  
  
-   **逆アセンブルします。** XML 逆アセンブラー コンポーネントを含んでいます。  
  
-   **検証します。** 空  
  
-   **パーティの解決。** 証明書サブジェクトまたは送信元セキュリティ ID をパーティ ID に解決する、パーティの解決パイプライン コンポーネントを実行します。  
  
## <a name="xmltransmit-pipeline"></a>XMLTransmit パイプライン  
 XML 送信パイプラインは、次のステージで構成されます。  
  
-   **プリアセンブルです。** 空  
  
-   **編成します。** XML アセンブラー コンポーネントを含んでいます。  
  
-   **エンコードします。** 空  
  
## <a name="see-also"></a>参照  
 [パイプラインの種類](../core/types-of-pipelines.md)   
 [パイプライン コンポーネントの種類](../core/types-of-pipeline-components.md)   
 [パイプライン テンプレート](../core/pipeline-templates.md)   
 [パイプライン コンポーネント](../core/pipeline-components.md)   
 [パイプライン、ステージ、およびコンポーネントについて](../core/about-pipelines-stages-and-components.md)