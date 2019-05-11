---
title: 既定のパイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a49e806bf8d38c7b2018f583e443589065be71a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389711"
---
# <a name="default-pipelines"></a>既定のパイプライン
ときに既定のパイプラインを作成し、既定で展開新しいアプリケーションを作成し、すべての BizTalk プロジェクトに対して、\References フォルダーの Microsoft.BizTalk.DefaultPipelines アセンブリに表示されます。 パイプライン デザイナーで、既定のパイプラインを変更できません。 これらのパイプラインは、送信ポートを構成するときに選択するか、BizTalk エクスプ ローラーで受信場所。 このトピックでは、既定のパイプラインとそれらを使用する場合について説明します。  
  
> [!NOTE]
>  XML 受信パイプラインおよび XML 送信パイプラインは 4 ギガバイトを超える XML ドキュメントをサポートしていません。  
  
## <a name="passthrureceive-pipeline"></a>PassThruReceive パイプライン  
 パススルー受信パイプラインには、コンポーネントがありません。 メッセージ ペイロードの処理が必要ないときに単純なパススルー シナリオで使用されます。 このパイプラインは通常、ソースと、メッセージの送信先が既知であり、メッセージ エンコーディング、または逆アセンブル、検証は必要ないときに使用します。 このパイプラインは、パススルー送信パイプラインと組み合わせてよく使用されます。  
  
 逆アセンブラーを含まないために、オーケストレーションにメッセージをルーティングするパススルー受信パイプラインを使用できません。  
  
> [!NOTE]
>  パススルー受信パイプラインは、プロパティの昇格をサポートしていません。  
  
## <a name="passthrutransmit-pipeline"></a>PassThruTransmit パイプライン  
 パススルー送信パイプラインには、コンポーネントがありません。 このパイプラインは通常、変換先にメッセージを送信する前に必要なドキュメントの処理がないときに使用します。  
  
## <a name="xmlreceive-pipeline"></a>XMLReceive パイプライン  
 XML 受信パイプラインは、次のステージで構成されます。  
  
-   **デコードします。** 空  
  
-   **逆アセンブルします。** XML 逆アセンブラー コンポーネントが含まれています  
  
-   **検証します。** 空  
  
-   **パーティの解決。** 証明書のサブジェクトまたは送信元セキュリティ ID をパーティ ID に解決されるパーティの解決コンポーネントを実行します  
  
## <a name="xmltransmit-pipeline"></a>XMLTransmit パイプライン  
 XML 送信パイプラインは、次のステージで構成されます。  
  
-   **プリアセンブルします。** 空  
  
-   **アセンブルします。** XML アセンブラー コンポーネントが含まれています  
  
-   **エンコードします。** 空  
  
## <a name="see-also"></a>参照  
 [パイプラインの種類](../core/types-of-pipelines.md)   
 [パイプライン コンポーネントの種類](../core/types-of-pipeline-components.md)   
 [パイプライン テンプレート](../core/pipeline-templates.md)   
 [パイプライン コンポーネント](../core/pipeline-components.md)   
 [パイプライン、ステージ、およびコンポーネントについて](../core/about-pipelines-stages-and-components.md)