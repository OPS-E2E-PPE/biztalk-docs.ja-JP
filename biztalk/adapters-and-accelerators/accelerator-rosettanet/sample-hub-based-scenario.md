---
title: サンプルのハブベース シナリオ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- supply chains, examples
- hub-and-spoke systems
- supply chains, hub-and-spoke systems
- examples, supply chains
- trading partners, supply chains
ms.assetid: ee92c24d-a281-4950-a61e-9cb3bd08d291
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 774764c030b2e6d6f74770f8a1aa2682e5eb6d65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282063"
---
# <a name="sample-hub-based-scenario"></a>サンプルのハブベース シナリオ
多くのサプライ チェーン シナリオでは、企業が、各取引先に対して RNIF (RosettaNet Implementation Framework) 接続を構築します。 これにより、サプライ チェーン全体の通信を効率的に標準化できます。 このシナリオについては、「[サンプル サプライ チェーン シナリオ](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md)です。  
  
 サプライ チェーン全体のトランザクションを自動化するもう 1 つの選択肢として、統合システムのセットアップと管理を行う企業と契約するという方法があります。 これがハブベースのシナリオです。  
  
## <a name="how-a-hub-based-system-works"></a>ハブベース システムの動作  
 ハブベースのシステムでは、統合システムを契約している企業が RNIF 接続を使用してハブ企業に接続します。 次に、ハブ企業は必要とされる任意の電子的接続手段を使って、その企業のすべての取引先に接続します。 ハブ企業は、接続オプションを使用して、すべての取引先パートナーを提供します。RNIF 接続、EDI、フラット ファイル、Web アプリケーション、または非準拠の独自の接続。 通信システムの管理は、ハブ企業が担当します。 次の図に、このようなハブベース システムのしくみを示します。  
  
 ![(& m); 60変更なし & #62;。](../../adapters-and-accelerators/accelerator-rosettanet/media/hub-based-scenario.gif "Hub_Based_Scenario")  
  
 ハブベースのシステムには、以下のような多くの利点があります。  
  
-   契約する企業は複雑なサプライ チェーンを管理する必要がなくなります。これはハブ企業が担当します。  
  
-   契約する企業はシステムの保守やアップグレードを行う必要がなく、ダウンタイムに対して責任を負いません。ハブ企業がシステムの保守およびダウンタイムの責任を負います。  
  
-   契約する企業は、標準化、自動化、コスト節約、可視性といった RosettaNet 準拠システムの利点を享受できます。  
  
-   契約する企業は、さまざまな電子的接続手段を包括する完全自動サプライ チェーンを実現でき、取引先からの接続手段を制限する必要がなくなります。 契約する企業は、さまざまな接続方法に精通した技術担当者を雇用する必要がなくなります。  
  
-   取引先は、引き続き専用接続を使用することもできます (ハブ企業がサポートしている場合)。  
  
-   システムには柔軟性があります。 取引先では RosettaNet 準拠システムを採用する必要はありません。 ただし、採用すれば、このようなシステムの利点を享受できます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server がビジネス ニーズを解決する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [取引先との統合の必要性](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md)   
 [サプライ チェーンの課題](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md)   
 [サプライ チェーン ソリューション](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md)   
 [サンプル サプライ チェーン シナリオ](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md)