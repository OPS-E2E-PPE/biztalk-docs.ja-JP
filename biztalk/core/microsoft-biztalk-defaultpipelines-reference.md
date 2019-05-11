---
title: Microsoft.BizTalk.DefaultPipelines の参照 |Microsoft Docs
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
- pipelines
- PassThruTransmit pipelines
- XMLReceive pipelines
- pipelines, XMLTransmit
- Pipeline Designer
- pipelines, XMLReceive
- pipelines, about pipelines
- PassThruReceive pipelines
- XMLTransmit pipelines
- namespaces, Microsoft.BizTalk.DefaultPipelines namespace
- Microsoft.BizTalk.DefaultPipelines namespace
ms.assetid: a54f8813-9c6f-4afe-8c76-2db3fa478947
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a183aa499b5acb56813fcb0433d2fd57258a777d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324839"
---
# <a name="microsoftbiztalkdefaultpipelines-reference"></a>Microsoft.BizTalk.DefaultPipelines の参照
**Microsoft.BizTalk.DefaultPipelines**名前空間には、次のパイプラインが含まれています。  
  
- [Xmlreceive]  
  
- PassThruReceive  
  
- XMLTransmit  
  
- PassThruTransmit  
  
  パイプラインを定義し、受信または送信されたメッセージの処理の 1 つ以上のステージをリンクするソフトウェア コンポーネントとは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 各ステージには、エンコードまたはデコード、逆アセンブルまたはアセンブル、および復号化または暗号化などの関数が含まれます。 これらの関数は、特定の順序で実装されます。 パイプライン デザイナーを使用して、作成する受信パイプラインと送信されます。  
  
  BizTalk プロジェクトに含まれる既定のパイプライン参照を使用してドキュメントのすべての種類を処理できる、 **PassThruReceive**と**PassThruTransmit**パイプライン。  
  
  次の表は、既定のパイプラインの既定のコンポーネントを示します。 これらのリストには、各パイプラインにおけるコンポーネントの既定の順序も示します。 追加し、必要に応じて、コンポーネントを削除できます。  
  
  既定の XMLReceive パイプラインに既定のコンポーネントは次のとおりです。  
  
- 復号化  
  
- デコーダー  
  
- 逆アセンブラー  
  
- 検証ツール  
  
- パーティの解決  
  
  既定の XMLTransmit パイプラインで既定のコンポーネントは次のとおりです。  
  
- アセンブラー  
  
- エンコーダー  
  
- 盗み見  
  
## <a name="see-also"></a>参照  
 [パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md)   
 [BizTalk プロジェクト内の BizTalk 名前空間参照について](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)