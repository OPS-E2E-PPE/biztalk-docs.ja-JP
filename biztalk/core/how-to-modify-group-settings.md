---
title: 更新プログラム グループの設定 |Microsoft ドキュメント
description: BizTalk Server 管理コンソールを使用して、グループのパフォーマンス設定を変更します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe0cbeb8-23d6-45cf-8535-c989914f5124
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d5de48a504d649279a2e9e0184ff2069547f36a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254810"
---
# <a name="how-to-update-the-biztalk-group-settings"></a>BizTalk グループの設定を更新する方法
ダッシュボードの設定を使用すると、特定の BizTalk グループに属するすべてのコンピューターで使用する構成情報を変更できます。 ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でグループレベルのパフォーマンス設定を変更する手順について説明します。 これらの設定は特定のグループのすべてのコンピューターに適用できます。  
  
> [!NOTE]
>  また、ホストとホスト インスタンス設定も変更できます。 詳細については、次を参照してください。[ホスト設定を変更する方法](../core/how-to-modify-host-settings.md)と[ホスト インスタンス設定を変更する方法](../core/how-to-modify-host-instance-settings.md)です。  
  
 BizTalk Server の現在の設定は XML ファイルにエクスポートできます。 後で、新しい値を設定する代わりに、これらの設定を設定ダッシュボードにインポートできます。 インポートやエクスポートの詳細について、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定を参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)と[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)です。 
  
## <a name="prerequisites"></a>前提条件  
 この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。  
  
## <a name="update-the-group-level-settings"></a>グループ レベル設定を更新します。  
  
1.  **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**設定**です。  
  
2.  **BizTalk 設定ダッシュ ボード** ダイアログ ボックスで、**グループ** ページで、次の操作します。  
  
    |プロパティ|目的|境界値|既定値|アップグレード ロジック|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**構成の更新間隔**|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でメッセージング構成を更新する間隔を設定します。|1 - 43200|-|-|  
    |**メッセージ バッチしきい値**|受信メッセージ バッチの合計サイズがこの値を超えると、バッチは小さなバッチに分割されて処理されます。|1 - 10000000|102400|HKEY_LOCAL_MACHINE\Software\Microsoft\BizTalk Server\3.0\Administration\TransformThreshold の値をコピーします。|  
    |**大きなメッセージ サイズ**|バッチでのストリーミングまたは変換中のストリーミングをトリガーする個別メッセージのサイズのしきい値を設定します。|1 - 10000000|1000000|既存の最大**大きなメッセージ サイズ**と**LargeMessageFragmentSize**値。|  
    |**追跡とレポート**||-|-|-|  
    |**メッセージ ボックス パフォーマンス カウンターのサンプリング間隔**|パフォーマンス カウンターを更新する間隔を設定します。<br /><br /> 間隔により、データベースに対する負荷とカウンターの値の新しさがトレードオフされます。 値を大きくするとデータがあまり更新されなくなり、データベースに対する負荷が小さくなります。|1 – 整数型の最大値|-|BizTalk グループがあれば、そのコンピューターで最も大きな値。 そうでない場合は、既定値。|  
    |**グループ レベルの追跡を有効にします。**|このオプションを選択すると、BizTalk Server のグループ レベルの追跡が有効になります。<br /><br /> グローバル追跡を無効にすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループ全体の追跡インターセプターが無効になります。 つまり、BizTalk は追跡テーブル内のイベントを追跡しません。 **注:** この設定では、BAM の追跡は影響しません。|On、Off します。|基準|-|  
  
3.  をクリックして**適用**を変更を適用し、別のタブに進みます。をクリックしてまたは**OK**を変更を適用し、設定ダッシュ ボードを終了します。  
  
    > [!NOTE]
    >  既定の設定を復元する をクリックして**既定値に戻す**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)