---
title: "ポリシーの追跡を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, tracking
- HAT, policies
- managing [policies], tracking
- tracking, policies
- managing [policies], configuring
- policies, configuring
- configuring [HAT tracking], policies
- tracking, configuring
ms.assetid: f126e541-c183-4544-8b9d-ca07d2af303e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96fb7607bcdce8143901dabd3cdf6358f21a6a8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-policy"></a>ポリシーの追跡を構成する方法
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、ポリシーの追跡を構成する方法について説明します。 管理コンソールの [グループ ハブ] ページのクエリ ビューでインスタンス データ、条件の結果、アクション、および議題の更新を表示するオプションを選択できます。  
  
 詳細については、作成して、クエリを使用して、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)です。 メッセージとサービスのインスタンスの追跡機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-configure-tracking-for-a-policy"></a>ポリシーの追跡を構成するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、ポリシーの追跡を構成する BizTalk アプリケーションを展開します。  
  
3.  をクリックして**ポリシー**ポリシーを右クリックしをクリックして**プロパティ**、順にクリック**追跡**です。  
  
4.  次の表に示すように、必要な追跡オプションを選択し、クリックして**OK**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**高速なアクティビティ**|ポリシーが適用されるインスタンス データを追跡するには、このチェック ボックスをオンにします。|  
    |**条件の評価**|選択したポリシーの条件の結果 (True または False) を追跡するには、このチェック ボックスをオンにします。|  
    |**ルールの実行**|ポリシーの結果として開始されたアクションを追跡するには、このチェック ボックスをオンにします。|  
    |**議題の更新**|議題に加えられた変更を追跡するには、このチェック ボックスをオンにします。 議題とは、"True" が設定されており実行が必要なアクションの一覧です。|  
  
## <a name="see-also"></a>参照  
 [ポリシーの管理](../core/managing-policies.md)