---
title: システムの問題を分散 |Microsoft ドキュメント
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
ms.openlocfilehash: 24abe471a66e8bc0724ad731388c5a0e7c07b573
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297754"
---
# <a name="distributed-system-problems"></a>分散システムの問題
分散の送信先システムでのジョブは、復元は、他のコンピューター上の問題やエラーの認識しません。 たとえば、コンピューター A が BizTalk 管理データベースおよび BizTalk 追跡データベース、復元して、コンピューター B が BizTalk メッセージ ボックス データベースを復元することです。 両方のコンピューターでは、1 ~ 25 のバックアップ セットが正常に復元します。 ただし、セット 26 には、BizTalk メッセージ ボックス データベースの破損したログ バックアップ ファイルがあります。 コンピューター A は、そのデータベースを正しく復元が、コンピューター B が破損したファイルの復元に失敗します。  
  
 このような状況で元システムで完全バックアップを強制します。 上記の例に続ける場合と、問題の診断セット 35 の完全バックアップが作成されました。 復元セット 34 26、その後、コンピューター A はコンピューター B のコンピューター上の問題を認識してないためされるまでは失敗が完全バックアップは 35 を設定し、それ以降のログのバックアップ セットの 36 (前述のとおり必要があるが常に復元する一連の 1 つの後続の完全なログ バックアップをします。d)。 コンピューター B で 35 と 36 のセットが届いたら、その 35 を使用してそれ自体を修復します。 修復が完了したら、コンピューター A と B が同期されます。  
  
## <a name="see-also"></a>参照  
 [ログ配布のトラブルシューティング](../technical-guides/troubleshooting-log-shipping.md)