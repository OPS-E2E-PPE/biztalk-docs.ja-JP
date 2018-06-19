---
title: ソース システムの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 722dd52c-1eea-453c-9a36-9b8d9cf19350
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73f5d785c20d1390ae811d737e9169951e0270e7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009307"
---
# <a name="configuring-the-source-system"></a>ソース システムを構成します。
BizTalk Server のログ配布のために、必要はありません、送信元システムは、1 つ上にある場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスまたはかどうかは、Windows Server クラスターでホストされている複数のインスタンス間で分散されます。 BizTalk Server のバックアップ ジョブを正常に実行するために必要な追加の考慮事項はありません。 このジョブを構成するのを参照してください。[を BizTalk Server のバックアップ ジョブを構成する方法](http://go.microsoft.com/fwlink/?LinkID=154072)(http://go.microsoft.com/fwlink/?LinkID=154072)、BizTalk Server のヘルプ。 BizTalk Server のバックアップ ジョブを構成した後、トピックに進んで[を送信先システムを構成する方法](../technical-guides/how-to-configure-the-destination-system.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のログ配布の構成](../technical-guides/configuring-biztalk-server-log-shipping.md)