---
title: ディザスター リカバリーのための構成 |Microsoft Docs
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
ms.openlocfilehash: f0bce395a5873947d006aa84b620b921a4a8e943
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253555"
---
# <a name="configuring-for-disaster-recovery"></a>ディザスター リカバリーを構成します。
既存のバックアップを拡張する BizTalk Server のログ配布機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブ。 BizTalk Server のログ配布、一連のバックアップのジョブによって生成されたバックアップ セットを手動で復元する必要はありませんし、システム障害が発生した場合のダウンタイムを短縮します。 BizTalk Server のログ配布は、BizTalk のディザスター リカバリーの手順の重要なコンポーネントです。  
  
> [!NOTE]  
>  各アプリケーション チームがこのトピックで説明する概念を補完するディザスター リカバリー計画を復元し、文書化されているバックアップがある必要があります。 全体的な計画は、アプリケーションやオペレーティング システムのコンポーネントを含めて、システム全体に対処する必要があります。  
  
 手動での新しいセットを BizTalk グループの復元を実行するとよく似ていますディザスター リカバリー操作を実行して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンス。 主な違いは、その BizTalk Server ログ配布には、多くの手動手順を保存、ディザスター リカバリー サイトに継続的にログが適用されます。 そのため、ログの最後のセットにのみ必要があります手動で復元するときに BizTalk Server のログ配布を実装します。 それ以外の場合、前回の完全バックアップ以降のすべてのログ バックアップ後に、前回の完全バックアップは、手動で復元する必要があります。 BizTalk Server ログ配布は、この手動プロセスで、ディザスター リカバリー サイトの復元を高速化労力を減らします。  
  
 このセクションでは、ディザスター リカバリーのプロセスを容易に運用環境の構成に関する推奨事項について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ディザスター リカバリー サイトの準備](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [ログ配布のユーザー アカウントとロール](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [BizTalk Server のログ配布の構成](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a>参照  
 [ディザスター リカバリー](../technical-guides/disaster-recovery.md)