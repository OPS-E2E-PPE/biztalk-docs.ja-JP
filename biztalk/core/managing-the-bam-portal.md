---
title: BizTalk Server で BAM ポータルの管理 |Microsoft Docs
Description: インストールして、BizTalk Server で BAM ポータルの構成の概要
ms.custom: ''
ms.date: 08/15/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a08aa85-3a45-4a8c-bdb5-5615ca097ce1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0448e435e7adcc84d30f31ded54534c248e8e69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380155"
---
# <a name="manage-the-bam-portal"></a>BAM ポータルを管理します。

## <a name="set-up-bam-portal"></a>BAM ポータルをセットアップします。
管理者を実行して BAM ポータルの設定、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。 BizTalk Server 構成ツールを使用して、BAM が有効になっているかどうかを指定して、ポータルを表示できる Windows グループと、ポータルをホストする Web サイトでは、Web サービスのアカウントを指定します。 BAM ポータルを設定すると、BAM ポータルの構成を更新するために必要になると、構成ツールを使用してポータル ユーザー グループ、アプリケーション プール アカウント、および管理 Web サービスのユーザーなどの構成設定を更新します。  
  
 BAM ポータルのインストールの詳細については、次を参照してください。[複数コンピュータ環境での BAM の構成のインストールおよび](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)します。  
  
 BAM ポータルを構成する方法の詳細については、次を参照してください。 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)します。
  
 BAM ポータルでは、webconfig.xml ファイルを変更することによってアクセスされる多くのカスタマイズ可能な設定があります。 これらの設定は、パフォーマンスと、BAM ポータルの操作を制御します。 このセクションの残りのこの部分では、BAM ポータル構成をカスタマイズする方法について説明します。  
  
## <a name="next-steps"></a>次のステップ 
  
-   [BAM ポータルの構成のカスタマイズ](../core/customizing-the-bam-portal-configuration.md)  
  
-   [NLB クラスターで機能する BAM ポータルを構成する方法](../core/how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster.md)  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)