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
ms.openlocfilehash: 7735617b0d70aa3c693b1808b07d7670e6137f15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999339"
---
# <a name="what-is-biztalk-server-log-shipping"></a>BizTalk Server ログ配布とですか。
BizTalk Server のディザスター リカバリーの手順は、BizTalk を中心に構築された、ログ配布します。 BizTalk ログ配布は継続的に障害回復サイトのデータベースにトランザクション ログの更新プログラムを適用することで、災害発生時のデータベースの復元を簡略化します。  
  
 BizTalk ログ配布と同様の原則に基づいて while[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログ配布、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログ配布はサポートされていません、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースがバックアップ BizTalk Server の SQL エージェント ジョブの一部としてバックアップします。  
  
## <a name="how-does-biztalk-log-shipping-work"></a>BizTalk ログ配布作業がどのようにか。  
 BizTalk のログ配布と同様の方法で関数[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログ配布します。 実稼働[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をバックアップするグループが構成されている、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] UNC の場所へのデータベース。 既定では、1 時間ごとの完全バックアップとログのバックアップを 15 分ごと、バックアップの BizTalk SQL エージェント ジョブを実行します。 BizTalk Server のバックアップ ジョブは、バックアップの失敗が検出された場合、完全バックアップを自動的に開始するためのロジックを実装します。  
  
 ときに、ディザスター リカバリー [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] BizTalk ログ配布、バックアップ ジョブ、復元、ディザスター リカバリー サイトで 15 分ごと既定では BizTalk Server SQL エージェントによって作成されたバックアップ ファイルのインスタンスが構成されます。 バックアップ ファイルは、SQL の復元コマンドで、ネットワーク経由でコピーされます。 次の状況でのみ、完全バックアップのファイルがコピーされます。  
  
- BizTalk ログ配布が構成最初  
  
- ときに新しいデータベースは、BizTalk Server のバックアップ ジョブに追加されます。  
  
- ディザスター リカバリー サイトでの復元エラーの発生時  
  
  各[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスのディザスター リカバリー サイトには、運用環境でホストされるデータベースを復元する BizTalk ログ配布の一部として個別に構成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンス。 ときに、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] BizTalk Server のインスタンスが構成されているログ配布と**BTS ログ配布データベースの復元**ジョブが有効になっている、 **BTS ログ配布データベースの復元**ジョブへの接続は、運用環境で BizTalk 管理データベース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  
  
  上述のよう、移行先サーバーが最初に構成されている場合、データベースの完全バックアップが移行先サーバーに復元されます。 ほとんどのログのみが復元されたときに、 **BTS ログ配布データベースの復元**ジョブが実行されます。  
  
  ディザスター リカバリーを表示するときに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio で、データベースが「読み込み中」状態で表示されます。 これは、バックアップ セットの最後のログが自動的に復元しないためにです。 新しいログが使用可能、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布は、最後のログに、[次へ] を復元します。 ディザスター リカバリーのイベントが発生して、ディザスター リカバリー サイトをオンラインにする必要があります、STOPATMARK コマンドを使用して、データベースを復旧する最後のログを復元し、データベースは「読み込み中」状態にあるものとして表示されなくされます。