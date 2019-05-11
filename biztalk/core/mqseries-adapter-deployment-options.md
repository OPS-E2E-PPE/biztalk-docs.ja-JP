---
title: MQSeries アダプターの展開オプション |Microsoft Docs
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
ms.openlocfilehash: 18d2791b62478b1927772149f3f5d54f3cb5f618
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65264416"
---
# <a name="mqseries-adapter-deployment-options"></a>MQSeries アダプターの展開オプション
MQSeries アダプターでは、ハードウェアの構成で優れた柔軟性を提供します。 これには少なくとも 3 つの主な使用パターンがあります。  
  
-   BizTalk Server、アダプター、および MQSeries Server for Windows を同じコンピューターにします。  
  
-   BizTalk Server と MQSeries Server を実行している 1 つまたは複数の追加コンピューターに接続する 2 番目のコンピューター上の 1 台のコンピューターと MQSeries Server for Windows (MQSAgent を含む) のアダプター。  
  
-   別のコンピューター グループとアダプター、MQSeries Server が (MQSAgent を含む) に複数の BizTalk Server インストールします。  
  
-   MQSeries Server と MQSeries キュー マネージャーをクラスター化する場合、アダプターが正しく機能します。  
  
    > [!NOTE]
    >  MQSAgent COM + アプリケーションは、ここでクラスター化する必要がありますされません。 代わりに、クラスターの両方のノードでは、MQSAgent COM + アプリケーションをインストールおよび構成されている場合があります。 このシナリオで、MQSAgent COM + アプリケーションが停止した場合、クライアントから次の呼び出しを再起動します。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターの使用](../core/using-the-mqseries-adapter.md)