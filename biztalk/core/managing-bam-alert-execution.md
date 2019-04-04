---
title: BAM 警告の実行の管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], executing alerts
- Notification Services, configuration files
- BAM Management utility
- alerts, executing
ms.assetid: 44bb738e-fa2c-4b32-9e8d-e756d6c3778e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d8dca3f99480b6875253eb6aca102977935160b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021984"
---
# <a name="managing-bam-alert-execution"></a>BAM 警告の実行の管理
BAM 警告の実行は、BAM ポータル、BAM 管理ユーティリティ、および ProcessBamNSFiles.vbs スクリプトの 3 つの方法で変更できます。  
  
## <a name="bam-portal"></a>BAM ポータル  
 ナレッジ ワーカーおよび管理者は、警告の配信方法を BAM ポータルの警告マネージャーを使用して変更できます。 BAM ポータルからは、警告の有効と無効の切り替え、しきい値レベルの変更、配信場所の変更を実行できます。また、警告の実行に影響を与えるようなその他の操作も実行できます。  
  
 アラートを変更する方法の詳細については、[BAM ポータル ページで、警告マネージャー](../core/alert-manager-on-the-bam-portal-page.md)と[BAM ポータルのアラート](../core/alerts-in-the-bam-portal.md)を参照してください。  
  
### <a name="bam-management-utility"></a>BAM 管理ユーティリティ  
 管理者は、BAM 管理ユーティリティを使用して、警告の有効化、無効化、および削除を実行できます。  
  
 BAM 管理ユーティリティを使用して警告を管理する方法については、次のトピックを参照してください。  
  
-   [アラートを有効にする方法](../core/how-to-enable-alerts.md) 
  
-   [アラートを無効にする方法](../core/how-to-disable-alerts.md)  
  
-   [BAM 警告を削除する方法](../core/how-to-remove-bam-alerts.md)  
  
### <a name="modifying-notification-services-configuration-files"></a>Notification Services 構成ファイルの変更  
 管理者は、ProcessBamNSFiles.vbs スクリプトを使用して、Notification Services で警告を配信する方法を変更できます。 Notification Services の詳細については、アプリケーション定義ファイル (ADF)、[ http://go.microsoft.com/fwlink/?LinkId=127016](http://go.microsoft.com/fwlink/?LinkId=127016)を参照してください。  
  
 BAM に関連付けられた ADF を変更するには、次の一般的な手順を実行します。  
  
1. スクリプトを実行して、現在の構成ファイルと ADF ファイルを入手します。  
  
2. ファイルを変更します。  
  
3. スクリプトを実行して、変更を適用します。  
  
   ProcessBamNSFiles.vbs スクリプトの詳細については、[通知サービス構成ファイル用の BAM コマンド ライン スクリプト](../core/bam-command-line-script-for-notification-services-configuration-files.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [BAM ポータルの管理](../core/managing-the-bam-portal.md)   
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)