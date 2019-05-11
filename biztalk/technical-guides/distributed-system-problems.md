---
title: 分散システムの問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 287b0adb-d5f9-4e47-80f8-0ba5d90c7864
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674af4da96fe62c4955ea93af5c2026f850dafe6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305712"
---
# <a name="distributed-system-problems"></a>分散システムの問題
分散型の変換先のシステムで、復元ジョブの対象はエラーまたはその他のコンピューター上の問題の認識しません。 たとえば、コンピューター A は、BizTalk 管理データベースと BizTalk 追跡データベースを復元して、コンピューター B が BizTalk メッセージ ボックス データベースを復元することです。 両方のコンピューターでは、1 ~ 25 のバックアップ セットが正常に復元します。 ただし、セット、26 には、BizTalk メッセージ ボックス データベースの破損したログ バックアップ ファイルがあります。 コンピューター A は、そのデータベースを正しく復元しますが、破損したファイルを復元するコンピューター B が失敗します。  
  
 このような状況で、ソース システム上完全バックアップを強制します。 上記の例を続行するには、問題の診断を 35 のセットの完全バックアップが作成されたものとします。 完全バックアップは 35 を設定し、それ以降のログのバックアップ セットの 36 (覚えて必要があるが常に一連の 1 つの後続の完全なログ バックアップが復元されるまでコンピューター B のコンピューター上の問題を認識してではないために、失敗復元セット 34 26、その後、コンピューター Ad)。 35 から 36 のセットがコンピューター B に届いたら、その 35 を使用して自身を修復します。 修復が完了したら、コンピューター A と B が同期されます。  
  
## <a name="see-also"></a>参照  
 [ログ配布のトラブルシューティング](../technical-guides/troubleshooting-log-shipping.md)