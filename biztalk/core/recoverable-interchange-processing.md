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
# <a name="recoverable-interchange-processing"></a>回復可能なインターチェンジ処理
このセクションについて説明します**回復可能なインターチェンジ処理**により、次のステージまたはフェーズで、インターチェンジの 1 つまたは複数のメッセージが失敗した場合でも完全に処理するインターチェンジの機能。  
  
- 受信パイプラインの逆アセンブリ ステージ  
  
- 受信パイプラインの XML 検証ステージ  
  
- 受信ポートのマップ実行フェーズ  
  
  回復可能なインターチェンジ処理ができるように、有効なメッセージはメッセージの経路を通じて伝達され、無効なメッセージは、複数の識別可能なメッセージを含む 1 つのインターチェンジを正常に処理をサポートする必要があるよう促されて中断されています。 標準のインターチェンジ処理では、特定のインターチェンジに無効なメッセージが存在すると、インターチェンジ全体を 1 つまたは複数の有効なメッセージが含まれている場合でも中断します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [逆アセンブリ ステージ (回復可能なインターチェンジ処理)](../core/disassembly-stage-recoverable-interchange-processing.md)  
  
-   [XML 検証ステージ (回復可能なインターチェンジ処理)](../core/xml-validation-stage-recoverable-interchange-processing.md)  
  
-   [マッピング フェーズ (回復可能なインターチェンジ処理)](../core/mapping-phase-recoverable-interchange-processing.md)