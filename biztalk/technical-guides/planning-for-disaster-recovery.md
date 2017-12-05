---
title: "障害回復の計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a33e8875-cfde-4a60-9dab-fc6bb3ac4f1c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3619a34c843665750abd4f5d852b0f1af5210e1c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="planning-for-disaster-recovery"></a>災害時の復旧計画
このトピックでは、災害復旧の要件をアプリケーション チームと BizTalk Server 用の手順のガイダンスを提供します。 Microsoft BizTalk Server の構成と処理の情報を格納する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 BizTalk Server の高可用性と災害復旧処理は、高可用性と災害復旧の機能によって達成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。  
  
 BizTalk グループでホストされているデータベースのセットで定義[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 ホストされているデータベースのセット[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Windows Server クラスターを使用して高可用性を実現することができます。 BizTalk 環境を実行しているコンピューターで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を実行しているコンピューターで、「実行時環境」と、データベースを提供[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]環境の永続的ストアを提供します。 したがって、BizTalk Server のバックアップ、復元、および災害復旧の手順は、頻繁に重点を置きます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。  
  
## <a name="purpose"></a>用途  
 このトピックでは統合されて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主要なドキュメントや、各種の Microsoft Web サイトからの情報の障害復旧情報、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]製品チームの障害復旧手順を定義する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
 アプリケーション チームは、バックアップ、復元、および災害復旧の手順を徹底的にテストする必要があります。 手順は、実稼働環境に入る前にアプリケーションの要件を満たすに合わせてカスタマイズも確認する必要があります。  
  
## <a name="scope"></a>スコープ  
 このセクションでは、BizTalk Server との関連する手順の災害復旧の手順で焦点を当てています[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 このガイドは、バックアップし、BizTalk Server を復元する方法についての関連するドキュメントに基づいています。  
  
 バックアップと復元の詳細については、このドキュメントを参照して、参照してください[をバックアップおよび復元する BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071)、BizTalk Server のヘルプします。 各アプリケーション チームは、ドキュメントのコンピューター名、ドライブ文字など、環境固有の追加の手順では、このトピックの情報を拡張する必要があり、関連するクラスターの構成と同様の障害復旧手順ソリューションの一部である非 BizTalk アプリケーション。  
  
 このトピックでは、詳細な障害復旧手順は次の領域。  
  
-   非 BizTalk アプリケーション  
  
-   アプリケーションのソース コード  
  
-   証明書  
  
-   アプリケーションの操作  
  
 上記以外をアプリケーションの災害復旧計画でのドキュメントは、各アプリケーション チームによってアドレス指定する必要がありますを必要とするその他の領域がある可能性があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ディザスター リカバリーのベスト プラクティス](../technical-guides/best-practices-for-disaster-recovery.md)  
  
-   [BizTalk Server のログ配布の概要](../technical-guides/what-is-biztalk-server-log-shipping.md)