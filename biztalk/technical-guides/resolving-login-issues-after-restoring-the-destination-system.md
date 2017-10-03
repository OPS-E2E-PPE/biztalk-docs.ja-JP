---
title: "送信先システムを復元した後ログインの問題を解決する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9232ca3-dadb-4b3c-8ec4-4e307c32d2e5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e691e690552f6decb3eed5f55dd17295c21a4efd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="resolving-login-issues-after-restoring-the-destination-system"></a>送信先システムを復元した後ログインの問題を解決します。
ソース システムの構成によっては配置時に、「不明」なユーザーを解決する必要があります。 孤立したデータベース ユーザーは、対応するセキュリティを持たないユーザーのログイン[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 システム オンラインを使用して、取り込む前にこれらのユーザーの対応するログインを作成、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SQL Management Studio (で**セキュリティ**、**ログイン**)。 任意の時点では、これらのログインを作成することができますが、それらを作成することをお勧めとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布を構成します。  
  
 作成されたログインが Windows アカウントとグループに対応する際に使用される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と手動で作成され、いずれかで使用する任意のログインに、ソース システム上に構成された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-ロールを作成します。 ローカル Windows アカウントにこれらのログインが対応してまたはグループ、アカウントおよびグループ必要がありますまず前に作成するログインを追加することができます。 BizTalk server のコンピューター名が変更されていない場合は、ローカル アカウントやグループのログインに関連付けられているユーザーを解決します。  
  
 構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布、Microsoft サポート技術情報の記事 918992 の手順に従って[SQL Server 2005 のインスタンスと SQL Server 2008 の間で、ログインおよびパスワードを転送する方法](http://go.microsoft.com/fwlink/?LinkId=157143)(http://go.microsoft.com/fwlink/ しますか。LinkId = 157143) 移行先サーバーに必要なログインを追加するスクリプトを作成します。  
  
## <a name="see-also"></a>参照  
 [ログ配布のトラブルシューティング](../technical-guides/troubleshooting-log-shipping.md)