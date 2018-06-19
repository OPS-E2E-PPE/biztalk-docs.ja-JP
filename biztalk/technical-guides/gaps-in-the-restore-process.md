---
title: 復元プロセスのギャップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 616c4f36-8ed6-4b99-b97a-5635627dfc17
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b7d3ccadd950f5a955430b982c1a6f79a262864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298098"
---
# <a name="gaps-in-the-restore-process"></a>復元プロセスのギャップ
Master.dbo.bts_LogShippingHistory テーブルのレコードを確認するには、復元されたセット内のギャップがわかります。 これにはいくつかの理由が考えられます。 ただし、ギャップが発生した場合でも、送信先システムの安定性を復元することができます。 ギャップの後に、送信先の環境を修復する設定の完全バックアップの復元を指定する必要があります。 ギャップが続いていない場合、完全バックアップの復元の設定、先の環境が安定しない一貫した状態に復元することはできません。  
  
> [!NOTE]  
>  本来、完全バックアップを復元する目的は、データベースの初期状態を作成したり、ログ履歴バックアップ チェーンの問題を修復したりすることです。 復元で問題が発生しない限り、完全バックアップ セットは復元されません、ログ バックアップ チェーンに、参加していないためです。  
  
## <a name="see-also"></a>参照  
 [ログ配布のトラブルシューティング](../technical-guides/troubleshooting-log-shipping.md)