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
ms.openlocfilehash: de2ec54b34a4e6d92f471db7fe9ad5dbc7933014
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022056"
---
# <a name="microsoftbiztalkdefaultpipelines-reference"></a>Microsoft.BizTalk.DefaultPipelines の参照
**Microsoft.BizTalk.DefaultPipelines**名前空間には、次のパイプラインが含まれています。  
  
- XMLReceive  
  
- PassThruReceive  
  
- XMLTransmit  
  
- PassThruTransmit  
  
  パイプラインとは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で送受信されるメッセージを処理するために 1 つ以上のステージを定義およびリンクする、ソフトウェア コンポーネントです。 ステージは、エンコードやデコード、アセンブルや逆アセンブル、暗号化や復号化などの機能を備えています。 これらの機能は、特定の順序で実装されます。 パイプライン デザイナーを使用して、受信および送信パイプラインを作成できます。  
  
  BizTalk プロジェクトに含まれる既定のパイプライン参照を使用してドキュメントのすべての種類を処理できる、 **PassThruReceive**と**PassThruTransmit**パイプライン。  
  
  既定のパイプラインに含まれる既定のコンポーネントを次に示します。 これらは、各パイプラインにおけるコンポーネントの既定の順序も示しています。 コンポーネントは必要に応じて追加したり削除したりできます。  
  
  既定の XMLReceive パイプラインに含まれる既定のコンポーネントは次のとおりです。  
  
- 復号化  
  
- デコーダー  
  
- 逆アセンブラー  
  
- 検証ツール  
  
- パーティの解決  
  
  既定の XMLTransmit パイプラインに含まれる既定のコンポーネントは次のとおりです。  
  
- アセンブラー  
  
- エンコーダー  
  
- 暗号化  
  
## <a name="see-also"></a>参照  
 [パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md)   
 [BizTalk プロジェクト内の BizTalk 名前空間参照について](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)