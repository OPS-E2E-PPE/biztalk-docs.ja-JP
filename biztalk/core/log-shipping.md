---
title: ログ配布 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- log shipping
ms.assetid: 25bc9724-1c99-43d0-8cd1-3ed8eaa60268
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd90e23fc99988bb134a77befe3195ca507037d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262114"
---
# <a name="log-shipping"></a>ログ配布
ログ配布は、システム障害時のダウンタイムを短縮することを目的とした、スタンバイ サーバーの機能です。ウォーム バックアップと呼ばれることもあります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には分散データベース設計が採用されているため、バックアップを作成する際は、その復元ポイントをデータベース間で同期させる必要があります。 トランザクションは、複数のデータベースにまたがる場合もあります。いずれか 1 つのデータベースで障害が発生し、復元する必要が生じた場合、関連するすべてのデータベースを特定のポイントまで復元しないと、システムの一貫した状態を維持することができなくなります。 ただし、必ずしもすべてのデータベースが分散トランザクションに参加しているとは限りません。 詳細については、次を参照してください。[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)です。  
  
 BizTalk Server のバックアップ ジョブでは、データベースのバックアップ セットを生成するプロセスを自動化するために、Microsoft SQL Server のログ マーキング機能を使用しています。 バックアップ セットには、同期された復元ポイントが定義されています。 BizTalk Server のバックアップ ジョブによって生成された一連のデータベースを復元するプロセスでは、各データベースの最後のログ バックアップ ファイルが、特定のログ マーク (最後から 2 番目のマーク) まで復元されます。 これにより、各データベースの状態が確実に復元され、データの損失を最小限に抑えることが可能となります。 重要なことは、最後から 2 番目のログ マークが使用されるという点です。 ログ配布機能は SQL Server にも備わっていますが、BizTalk Server のデータベースをバックアップおよび復元する場合は、BizTalk Server のログ配布機能のみを使用してください。  
  
> [!NOTE]
>  単純復旧モデルはトランザクション ログをバックアップせず、したがって最新のバックアップ以降のアクティビティの記録を保持していないので、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースでの SQL Server 単純復旧モデルの使用はサポートされません。  完全復旧モデルを使用するように SQL Server を構成して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベース バックアップ セットのデータの整合性を確保します。  
  
## <a name="see-also"></a>参照  
 [バックアップと復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)