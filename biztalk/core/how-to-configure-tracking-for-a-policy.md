---
title: ポリシーの追跡を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f92e8555c0d644411c165284dd734eb94e6569e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980411"
---
# <a name="how-to-configure-tracking-for-a-policy"></a>ポリシーの追跡を構成する方法
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、ポリシーの追跡を構成する方法について説明します。 管理コンソールの [グループ ハブ] ページのクエリ ビューでインスタンス データ、条件の結果、アクション、および議題の更新を表示するオプションを選択できます。  
  
 作成とクエリの使用に関する詳細については、[、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)を参照してください。 メッセージとサービスのインスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-tracking-for-a-policy"></a>ポリシーの追跡を構成するには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、ポリシーの追跡を構成する BizTalk アプリケーションを展開します。  
  
3. クリックして**ポリシー**は、ポリシーを右クリックし、**プロパティ**、順にクリックします**追跡**します。  
  
4. 次の表に示すように、必要な追跡オプションを選択し、クリックして**OK**します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**ファクト アクティビティ**|ポリシーが適用されるインスタンス データを追跡するには、このチェック ボックスをオンにします。|  
   |**条件の評価**|選択したポリシーの条件の結果 (True または False) を追跡するには、このチェック ボックスをオンにします。|  
   |**ルールの実行**|ポリシーの結果として開始されたアクションを追跡するには、このチェック ボックスをオンにします。|  
   |**議題の更新**|議題に加えられた変更を追跡するには、このチェック ボックスをオンにします。 議題とは、"True" が設定されており実行が必要なアクションの一覧です。|  
  
## <a name="see-also"></a>参照  
 [ポリシーの管理](../core/managing-policies.md)