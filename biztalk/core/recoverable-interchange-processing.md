---
title: 回復可能なインターチェンジ処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interchange processing [Messaging Engine], modes
- parties, party resolution
- Messaging Engine, examples
- messages, interchange modes
- interchange processing [Messaging Engine], examples
- Messaging Engine, Recoverable Interchange Processing property
- Messaging Engine, failures
- interchange processing [Messaging Engine], party resolution
- Messaging Engine, interchange processing
- disassembly stage, pipelines
- Recoverable Interchange Processing property
- Messaging Engine, interchange modes
- receive pipelines, disassembly stage
- interchange processing [Messaging Engine], failures
- interchange processing [Messaging Engine], restrictions
- System.Xml.XmlReader
- interchange modes [Messaging Engine]
ms.assetid: d9e366fe-b2a0-4f1a-b6b9-1264717e4731
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f61cd972466c912391e2ae899d00e6b92c2e13c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398039"
---
# <a name="recoverable-interchange-processing"></a><span data-ttu-id="e3acf-102">回復可能なインターチェンジ処理</span><span class="sxs-lookup"><span data-stu-id="e3acf-102">Recoverable Interchange Processing</span></span>
<span data-ttu-id="e3acf-103">このセクションについて説明します**回復可能なインターチェンジ処理**により、次のステージまたはフェーズで、インターチェンジの 1 つまたは複数のメッセージが失敗した場合でも完全に処理するインターチェンジの機能。</span><span class="sxs-lookup"><span data-stu-id="e3acf-103">This section discusses **recoverable interchange processing** feature, which allows an interchange to be processed completely even if one or more messages in the interchange fail at the following stages/phases:</span></span>  
  
- <span data-ttu-id="e3acf-104">受信パイプラインの逆アセンブリ ステージ</span><span class="sxs-lookup"><span data-stu-id="e3acf-104">Disassembly stage of a receive pipeline</span></span>  
  
- <span data-ttu-id="e3acf-105">受信パイプラインの XML 検証ステージ</span><span class="sxs-lookup"><span data-stu-id="e3acf-105">XML validation stage of a receive pipeline</span></span>  
  
- <span data-ttu-id="e3acf-106">受信ポートのマップ実行フェーズ</span><span class="sxs-lookup"><span data-stu-id="e3acf-106">Map execution phase of a receive port</span></span>  
  
  <span data-ttu-id="e3acf-107">回復可能なインターチェンジ処理ができるように、有効なメッセージはメッセージの経路を通じて伝達され、無効なメッセージは、複数の識別可能なメッセージを含む 1 つのインターチェンジを正常に処理をサポートする必要があるよう促されて中断されています。</span><span class="sxs-lookup"><span data-stu-id="e3acf-107">Recoverable interchange processing is motivated by the need to support successful processing of a single interchange that contains multiple identifiable messages so that valid messages are propagated through the messaging pathway and invalid messages are suspended.</span></span> <span data-ttu-id="e3acf-108">標準のインターチェンジ処理では、特定のインターチェンジに無効なメッセージが存在すると、インターチェンジ全体を 1 つまたは複数の有効なメッセージが含まれている場合でも中断します。</span><span class="sxs-lookup"><span data-stu-id="e3acf-108">With standard interchange processing, the existence of any invalid message in a given interchange causes the entire interchange to be suspended even if it contains one or more valid messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3acf-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e3acf-109">In This Section</span></span>  
  
-   [<span data-ttu-id="e3acf-110">逆アセンブリ ステージ (回復可能なインターチェンジ処理)</span><span class="sxs-lookup"><span data-stu-id="e3acf-110">Disassembly Stage (Recoverable Interchange Processing)</span></span>](../core/disassembly-stage-recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="e3acf-111">XML 検証ステージ (回復可能なインターチェンジ処理)</span><span class="sxs-lookup"><span data-stu-id="e3acf-111">XML Validation Stage (Recoverable Interchange Processing)</span></span>](../core/xml-validation-stage-recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="e3acf-112">マッピング フェーズ (回復可能なインターチェンジ処理)</span><span class="sxs-lookup"><span data-stu-id="e3acf-112">Mapping Phase (Recoverable Interchange Processing)</span></span>](../core/mapping-phase-recoverable-interchange-processing.md)