---
title: "プロファイル管理ユーティリティの追跡を使用して追跡プロファイルを展開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking profiles, deploying
- deploying, tracking profiles
- bttdeploy.exe [BAM]
- managing [BAM], deploying tracking profiles
ms.assetid: b3023379-cae1-45fc-a773-2660d3e4abf1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dde3f351c583be9037127c060d02c98d12b2fcb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility"></a>追跡プロファイル管理ユーティリティを使用して追跡プロファイルを展開する方法
ビジネス マネージャーは、組織の特定のビジネス プロセスの管理や監視を強化するために、新しい追跡プロファイルの作成や既存のプロファイルの変更を行うようにソリューション開発者に依頼します。  
  
 ソリューション開発者は、追跡プロファイル エディター (TPE) を使用して、ビジネス アナリストが必要とするデータを定義します。  
  
 ソリューション開発者により、追跡プロファイルの作成または変更が行われたら、管理者はその変更を有効にしてデータを収集できるように、bttdeploy.exe コマンド ライン ユーティリティを使用して追跡プロファイルを展開します。 ソリューション開発者は TPE を使用して追跡プロファイルを展開できます。  
  
> [!IMPORTANT]
>  追跡プロファイルを展開するには、追跡プロファイルに関連付けられたアセンブリを展開する必要があります。  
  
> [!IMPORTANT]
>  このツールを使用するには、BizTalk® 管理者特権が必要です。  
  
### <a name="to-deploy-the-tracking-profile-from-the-command-line-utility"></a>コマンド ライン ユーティリティから追跡プロファイルを展開するには  
  
1.  コマンド プロンプトでディレクトリに移動\<インストール パス\>\Program Files\Microsoft BizTalk Server\<バージョン\>\Tracking\\です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
2.  型**bttdeploy.exe\<プロファイル名\>.btt**です。  
  
3.  Enter キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [ビジネス アクティビティの監視 (BAM)](../core/business-activity-monitoring-bam.md)