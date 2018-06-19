---
title: MQSeries アダプターの展開オプション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, deploying
- deploying, MQSeries adapters
ms.assetid: d9380aff-40ea-419b-88e2-1e2ec3f023cb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b88fa674c38df8b31c1954234846fd3939ed8568
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263018"
---
# <a name="mqseries-adapter-deployment-options"></a>MQSeries アダプターの展開オプション
MQSeries アダプターを使用すると、ハードウェアを非常に柔軟に構成できます。 その主な使用法には、少なくとも次の 3 つのパターンがあります。  
  
-   BizTalk Server、MQSeries アダプター、MQSeries Server for Windows を同一のコンピューターで実行します。  
  
-   BizTalk Server および MQSeries アダプターを 1 台のコンピューターで実行し、MQSeries Server for Windows (MQSAgent を含む) を 2 台目のコンピューターで実行します。2 台目のコンピューターは、MQSeries Server を実行している 1 台以上の別のコンピューターに接続します。  
  
-   グループ内の複数の BizTalk Server インストールと MQSeries アダプター、MQSeries Server (MQSAgent を含む) を別個のコンピューターで実行します。  
  
-   MQSeries Server と MQSeries キュー マネージャーをクラスター化しても、アダプターは正常に機能します。  
  
    > [!NOTE]
    >  この場合、MQSAgent COM+ アプリケーションはクラスター化しないでください。 その代わり、クラスターのいずれのノードにも、MQSAgent COM+ アプリケーションをインストールおよび構成してください。 こうしておくことで、MQSAgent COM+ アプリケーションが停止した場合、クライアントから次の呼び出しがあったときに再起動します。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプタの使用](../core/using-the-mqseries-adapter.md)