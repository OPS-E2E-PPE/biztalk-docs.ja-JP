---
title: "相互依存オーケストレーションを開発する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5464096e-66d8-48de-bc02-c754c5cfbada
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93f8d086a60487e144b02c01a393eb6f10a63b40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-develop-interdependent-orchestrations"></a>相互依存オーケストレーションを開発する方法
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、相互に依存する Web サービスを持つオーケストレーションのセットを開発できます。 このシナリオは、複数のオーケストレーションが、それらを呼び出すオーケストレーションのデータ型とポートのどちらか一方または両方を参照する場合に発生します。 この種類のシナリオの例は、次のような特徴で示すことができます。  
  
-   2 つ以上のオーケストレーションがあります。  
  
-   最初のオーケストレーション (Orch1) が、一方向の Web サービス呼び出しで 2 番目のオーケストレーション (Orch2) を呼び出します。  
  
-   Orch2 は、Web サービス呼び出しで Orch1 に応答します。  
  
 この種類のプロジェクトの一例は、次を参照してください。[チュートリアル 2: 発注プロセス](http://msdn.microsoft.com/library/a324ef1b-39b3-49ab-9719-a13f526cb467)です。  
  
### <a name="to-develop-two-interdependent-orchestrations-orch1-and-orch2"></a>相互に依存する 2 つのオーケストレーション Orch1 と Orch2 を開発するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、Web サービスとして公開される受信ポートを持つ Orch1 の部分的なバージョンを作成します。  
  
2.  Orch1 をコンパイルします。  
  
3.  Web サービス公開ウィザードを実行して、ポートを公開します。  
  
4.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、Orch1 の Web サービスを使用する Orch2 をすべて作成します。  
  
5.  Orch2 をコンパイルします。  
  
6.  Web サービス公開ウィザードを実行し、ポートを公開します。  
  
7.  必要に応じて、Orch2 の Web サービスを使用する Orch1 を作成します。  
  
8.  Orch1 を再コンパイルします。  
  
9. Orch1 と Orch2 を展開します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Web サービス公開ウィザードを使用してオーケストレーションを Web サービスとして公開する方法](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)