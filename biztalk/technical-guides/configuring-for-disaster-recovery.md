---
title: 災害復旧のための構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdafe68-c8bf-4064-afca-6dfd22d15052
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3899b27324fa00e0b5c630c7be4433f65a917a1b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010955"
---
# <a name="configuring-for-disaster-recovery"></a>災害復旧のための構成
既存のバックアップを拡張する BizTalk Server のログ配布機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブです。 BizTalk Server のログ配布バックアップ ジョブによって生成されるバックアップ セットの系列を手動で復元する必要があるし、システム障害時のダウンタイムを短縮します。 BizTalk Server のログ配布は、BizTalk の障害復旧手順の重要なコンポーネントです。  
  
> [!NOTE]  
>  各アプリケーション チームは、文書化されたバックアップがあるし、復元のこのトピックで説明する概念を補足する災害復旧の計画する必要があります。 全体的な計画は、アプリケーションおよびオペレーティング システムのコンポーネントを含め、システム全体に対処する必要があります。  
  
 新しいセットを BizTalk グループの復元を手動で実行するとよく似ていますが、障害復旧操作を実行する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンスです。 主な違いは、その BizTalk Server ログ配布は継続的に、障害復旧サイトで、多くの手動処理の保存ログを適用します。 そのため、ログの最後のセットにのみ必要があります手動で復元するときに BizTalk Server のログ配布を実装します。 それ以外の場合、前回の完全バックアップ以降のすべてのログ バックアップ後に、最後の完全バックアップは、手動で復元する必要があります。 BizTalk Server ログ配布がこの手動プロセスで、障害復旧サイトの復元を迅速化労力を削減します。  
  
 このセクションでは、障害復旧プロセスを容易にする production 構成に関する推奨事項について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ディザスター リカバリー サイトの準備](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [ログ配布のユーザー アカウントとロール](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [BizTalk Server のログ配布の構成](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a>参照  
 [ディザスター リカバリー](../technical-guides/disaster-recovery.md)