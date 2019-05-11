---
title: プロファイル管理ユーティリティの追跡を使用して追跡プロファイルを展開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, deploying
- deploying, tracking profiles
- bttdeploy.exe [BAM]
- managing [BAM], deploying tracking profiles
ms.assetid: b3023379-cae1-45fc-a773-2660d3e4abf1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c4402c8e2951e069c908e431fac203c582c80be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385267"
---
# <a name="how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility"></a>追跡プロファイル管理ユーティリティを使用して追跡プロファイルを展開する方法
ビジネス マネージャーは、ソリューション開発者は、新しい追跡プロファイルを作成またはより良く管理および、組織の特定のビジネス プロセスを監視するには、既存の変更を確認します。  
  
 ソリューション開発者は、ビジネス アナリストが必要とするデータを定義するのに追跡プロファイル エディター (TPE) を使用します。  
  
 ソリューション開発者作成または追跡プロファイルを変更し、後に、管理者が、bttdeploy.exe コマンド ライン ユーティリティを使用して、変更を有効にされ、データが収集されるように展開します。 ソリューション開発者は TPE を使用して追跡プロファイルを展開できます。  
  
> [!IMPORTANT]
>  追跡プロファイルを展開する前に、追跡プロファイルに関連付けられているアセンブリを配置する必要があります。  
  
> [!IMPORTANT]
>  このツールを使用するには、BizTalk® 管理者権限が必要です。  
  
### <a name="to-deploy-the-tracking-profile-from-the-command-line-utility"></a>コマンド ライン ユーティリティから追跡プロファイルを展開するには  
  
1.  コマンド プロンプトからディレクトリに移動します。\<インストール パス\>\Program Files\Microsoft BizTalk Server\<バージョン\>\Tracking\\します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
2.  型**bttdeploy.exe\<プロファイル名\>.btt**します。  
  
3.  Enter キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [ビジネス アクティビティの監視 (BAM)](../core/business-activity-monitoring-bam.md)