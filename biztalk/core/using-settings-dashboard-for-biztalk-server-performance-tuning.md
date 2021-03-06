---
title: BizTalk server 設定ダッシュ ボードを使用してパフォーマンスのチューニング |Microsoft Docs
description: BizTalk Server 管理の設定ダッシュ ボードを使用して、グループ、ホスト、およびホスト インスタンスの設定を更新するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb1ddac-1e8f-4928-9c70-8326ae64a734
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b906ccae0e17d79f5783a3689a517fe4cba310ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395392"
---
# <a name="use-settings-dashboard-for-biztalk-server-performance-tuning"></a>BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング

## <a name="overview"></a>概要
設定ダッシュボードを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のさまざまな設定を微調整してパフォーマンスを最適化することができます。 BizTalk グループ、BizTalk ホスト、および BizTalk ホスト インスタンスの設定を変更することもできます。  
  
- **グループ レベル設定**:グループ レベルで使用することができます、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]などの構成の更新間隔、最大メッセージ バッチ サイズ、グループ レベルの追跡などのプロパティを設定します。これらの設定は、BizTalk グループのすべてのマシンに適用されます。  
  
- **ホスト レベルの設定**:ホスト レベルでは、ホストの追跡、リソース ベースの制限、メッセージ処理の制限に関連するプロパティに関連するプロパティ、およびオーケストレーションの制限に関連するプロパティなどの設定を変更できます。 これらの設定は、選択したホストのすべてのインスタンスに適用されます。  
  
- **インスタンス レベルの設定をホスト**:ホスト インスタンス レベルでは、.NET CLR 設定やオーケストレーション メモリ制限に関連するプロパティを変更することができます。 これらの設定は、選択したホスト インスタンスにのみ適用されます。  
  
  BizTalk グループ、BizTalk ホスト、および BizTalk ホスト インスタンスの設定の詳細については、次を参照してください[グループ設定を変更する方法](../core/how-to-modify-group-settings.md)、[ホスト設定の変更方法](../core/how-to-modify-host-settings.md)、および[ホストを変更する方法。設定インスタンス](../core/how-to-modify-host-instance-settings.md)します。  
  
  設定ダッシュボードによって、同じである必要がない複数の展開で BizTalk の設定をインポート/エクスポートすることができます。 ユーザー インターフェイスを使用して、ターゲットとソースの展開の間でホストとホスト インスタンスをマップできます。 これによって、ホスト名、コンピューター名、またはそれぞれの数が異なる環境に設定を適用できます。 BizTalk の設定のインポート/エクスポートの詳細については、次を参照してください。[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンス設定を管理します。](../core/managing-biztalk-server-performance-settings.md)