---
title: 復元プロセスのギャップ |Microsoft Docs
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
ms.openlocfilehash: 06de30faec798fe57f30299051dc7f97db285bcf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279061"
---
# <a name="gaps-in-the-restore-process"></a>復元プロセスのギャップ
Master.dbo.bts_LogShippingHistory テーブルのレコードを確認する際に、復元されたセット内のギャップを確認できます。 これにはいくつかの理由が考えられます。 ただし、ギャップが発生した場合でも、送信先システムの安定性を復元できます。 ギャップの後に、送信先の環境を修復する設定の完全バックアップの復元する必要があります。 ギャップの後、完全バックアップの設定の復元、移行先の環境が安定しないと、一貫した状態で復元することはできません。  
  
> [!NOTE]  
>  本来、完全バックアップを復元する目的は、データベースの初期状態を作成したり、ログ履歴バックアップ チェーンの問題を修復したりすることです。 復元を使用した問題が発生しない限り、完全バックアップ セットは復元され、ログ バックアップ チェーンに、参加していないためです。  
  
## <a name="see-also"></a>参照  
 [ログ配布のトラブルシューティング](../technical-guides/troubleshooting-log-shipping.md)