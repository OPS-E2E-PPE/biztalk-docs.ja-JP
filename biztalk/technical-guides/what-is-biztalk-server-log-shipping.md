---
title: BizTalk Server ログ配布とですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79a2088a-ff36-4590-97c9-51d5bb245486
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3b20589229b1e3868f23c3823d2a26decc56081
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010499"
---
# <a name="what-is-biztalk-server-log-shipping"></a>BizTalk Server ログ配布とですか。
BizTalk Server の障害復旧手順が構築されています。 BizTalk ログ配布します。 BizTalk ログ配布は継続的に、障害復旧サイト データベースをトランザクション ログの更新プログラムを適用して、障害時におけるデータベースの復元を簡略化します。  
  
 While BizTalk ログ配布として同じ原則に基づいて[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログ配布、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログ配布はサポートされていません、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のデータベースが、Backup BizTalk Server の SQL エージェント ジョブの一部としてバックアップします。  
  
## <a name="how-does-biztalk-log-shipping-work"></a>BizTalk ログ配布の作業がどのようにしますか。  
 BizTalk でログ配布関数と同様の方法[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログ配布します。 実稼働[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をバックアップするグループが構成されている、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] UNC の場所へのデータベースです。 既定は、Backup BizTalk SQL エージェント ジョブは、1 時間ごとの完全バックアップおよび 15 分ごとのログ バックアップを実行します。 BizTalk Server のバックアップ ジョブでは、バックアップの失敗が検出された場合に、完全バックアップを自動的に開始するためのロジックを実装します。  
  
 場合、災害復旧[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスは BizTalk ログ配布、バックアップ ジョブは、障害復旧サイトで 15 分ごとで復元既定 BizTalk Server SQL エージェントによって作成されたバックアップ ファイルに構成します。 バックアップ ファイルは、SQL の復元のコマンドによって、ネットワーク経由でコピーされます。 次の状況でのみ完全バックアップ ファイルがコピーされます。  
  
-   配布が最初に構成される BizTalk ログ  
  
-   ときに、新しいデータベースは、BizTalk Server のバックアップ ジョブに追加されます。  
  
-   復元に失敗した場合、災害復旧サイト  
  
 各[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスの災害復旧サイトには、実稼働環境でホストされているデータベースを復元する BizTalk ログ配布の一部として個別に構成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンスです。 ときに、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] BizTalk Server のインスタンスが構成されているログ配布と**BTS ログ配布データベースの復元**ジョブが有効になっている、 **BTS ログ配布データベースの復元**ジョブが接続する、運用環境で BizTalk 管理データベース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
 前述のよう、移行先サーバーが最初に構成されている場合、移行先サーバーにデータベースの完全バックアップが復元されます。 ほとんどの場合のみのログが復元されたときに、 **BTS ログ配布データベースの復元**ジョブの実行。  
  
 災害復旧を表示するときに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio でのデータベースが「読み込み」状態で表示されます。 バックアップ セットの最後のログが自動的に復元しないためにです。 新しいログが使用可能、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布は、最後のログに、[次へ] を復元します。 障害復旧イベントの発生し障害復旧サイトをオンラインにする必要があります、STOPATMARK コマンドを使用してデータベースを回復する最後のログを復元し、データベースが不要になった「読み込み中」状態にあるものとして表示されます。