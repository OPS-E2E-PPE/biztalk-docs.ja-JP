---
title: BizTalk Server を自動化するパフォーマンスのチューニング |Microsoft Docs
description: BTSTask を使用して、インポートまたは BizTalk Server での環境間でのパフォーマンス設定をエクスポートするには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07ff73b5-25d9-4f3f-9a4b-127c0b843741
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35c0ad345a480f10350b6fdf8a4ecc6eae4e9e74
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530653"
---
# <a name="automate-biztalk-server-performance-tuning"></a>BizTalk Server の自動化のパフォーマンス チューニング

## <a name="overview"></a>概要
チューニングを自動化する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス設定をインポートする BizTalk の設定をエクスポートするか、またはを使用して設定を操作することによって[WMI](http://go.microsoft.com/fwlink/?LinkId=200464)します。  
  
 後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最適なパフォーマンスの環境を設定すると、エクスポートまたは XML ファイルに、BizTalk Server 設定をインポートすることができます。 インポート/エクスポートできます BizTalk Server の設定、設定ダッシュ ボードまたは BTSTask コマンド ライン ユーティリティを使用しています。 **BTSTask.exe**で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]により、BizTalk 管理者は、新しいスクリプトを作成するときに、BTSTask コマンドを使用します。  
  
 インポート/エクスポート BizTalk Server 設定について 1 つの環境から別の使用に[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]を参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)します。 
  
## <a name="next-steps"></a>次のステップ 
  
-   [BTSTask を使用して BizTalk の設定をインポートまたはエクスポートする](../core/how-to-import-biztalk-settings-using-btstask.md)  
  
- [BTSTask コマンド ライン リファレンス](btstask-command-line-reference.md)
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンス設定の管理](../core/managing-biztalk-server-performance-settings.md)