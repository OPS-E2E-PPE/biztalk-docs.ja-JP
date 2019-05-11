---
title: ディザスター リカバリーの計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a33e8875-cfde-4a60-9dab-fc6bb3ac4f1c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 415064960644356db37530b87ce0f591d5a23bb9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400707"
---
# <a name="planning-for-disaster-recovery"></a>ディザスター リカバリーの計画
このトピックでは、ディザスター リカバリーの要件のアプリケーション チームと BizTalk Server 用の手順のガイダンスを提供します。 Microsoft BizTalk Server の構成と処理の情報を格納する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 BizTalk Server の高可用性とディザスター リカバリーは、の高可用性とディザスター リカバリー機能によって実現[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。  
  
 ホストされているデータベースのセットを BizTalk グループが定義されている[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 ホストされているデータベースのセット[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Windows Server クラスターを使用して高可用性を実現することができます。 BizTalk 環境を実行しているコンピューターで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]「実行時環境」と、データベースを実行するコンピューターで提供[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]環境の永続的なストアを提供します。 そのため、BizTalk Server のバックアップ、復元、およびディザスター リカバリーに重点を置いて、頻度の高い[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。  
  
## <a name="purpose"></a>目的  
 このトピックでは統合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ディザスター リカバリーについては、主要なドキュメント、さまざまな Microsoft Web サイト、および情報から、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]製品チームのディザスター リカバリー手順を定義する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
 アプリケーション チームは、バックアップ、復元、および障害回復の手順を徹底的にテストする必要があります。 また、手順、運用環境に入る前にアプリケーションの要件を満たすに合わせてカスタマイズを確認する必要があります。  
  
## <a name="scope"></a>スコープ  
 BizTalk Server との関連する手順のディザスター リカバリー手順に関して、このセクションに焦点を当てます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 このガイドは、バックアップし、BizTalk Server を復元する方法についての関連ドキュメントに基づいています。  
  
 バックアップと復元に関する詳細については、このドキュメントを参照して、参照してください[をバックアップおよび復元する BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071) BizTalk Server のヘルプ。 各アプリケーション チームがドキュメントのコンピューター名、ドライブ文字など、環境固有の追加の手順では、このトピックの情報を強化する必要がありますおよび関連するクラスターの構成と同様のディザスター リカバリー手順ソリューションの一部である BizTalk 以外のアプリケーション。  
  
 このトピックでは、詳細な障害復旧手順、次の領域。  
  
- 非 BizTalk アプリケーション  
  
- アプリケーションのソース コード  
  
- 証明書  
  
- アプリケーションの操作  
  
  ドキュメントを上に挙げた以外、アプリケーションのディザスター リカバリー計画では、各アプリケーション チームでアドレス指定する必要がありますを必要とするその他の領域である可能性があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ディザスター リカバリーのベスト プラクティス](../technical-guides/best-practices-for-disaster-recovery.md)  
  
-   [BizTalk Server のログ配布の概要](../technical-guides/what-is-biztalk-server-log-shipping.md)