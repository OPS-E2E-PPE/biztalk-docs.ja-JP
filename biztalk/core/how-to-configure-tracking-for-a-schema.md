---
title: "スキーマの追跡を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, configuring
- managing [schemas], configuring
- configuring [HAT tracking], schemas
- configuring, schemas
- configuring, tracking
- HAT, schemas
- managing [schemas], tracking
- schemas, tracking
- tracking, configuring
- tracking, schemas
ms.assetid: b5f69c98-8824-43b1-8f21-d84b60ac5431
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e15cb2210062901786b179ec75fe3880dea660b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-schema"></a>スキーマの追跡を構成する方法
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、スキーマの追跡を構成する方法について説明します。 追跡を構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの [グループ ハブ] ページのクエリ ビューで、表示するメッセージのプロパティを指定します。  
  
 詳細については、作成して、クエリを使用して、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)です。 メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 追跡オプションを表示するだけの場合、BizTalk Server Operators グループのメンバーとしてログオンできます。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-configure-tracking-for-a-schema"></a>スキーマの追跡を構成するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**追跡を構成するスキーマが含まれる BizTalk グループを展開し、スキーマを含むアプリケーションを展開します。  
  
3.  をクリックして**スキーマ**、スキーマを右クリックし、クリックして**プロパティ**です。  
  
4.  左側のウィンドウでをクリックして**追跡**です。  
  
5.  クリックして、メッセージを追跡するために使用するプロパティを指定するには、次のいずれかの操作**OK**:  
  
    -   選択、**すべてのメッセージ プロパティを選択して**示されているすべてのプロパティを使用する チェック ボックスです。  
  
        > [!NOTE]
        >  このチェック ボックスは、昇格させたプロパティを含むスキーマに対してのみ選択できます。  
  
    -   使用する各プロパティのチェック ボックスをオンにします。  
  
        > [!NOTE]
        >  これは、昇格させたプロパティを含むスキーマに対してのみ使用できます。  
  
> [!NOTE]
>  メッセージの追跡によって、システムのパフォーマンスとストレージにオーバーヘッドが発生します。したがって、オプションは必要なもののみ選択してください。  
  
## <a name="see-also"></a>参照  
 [スキーマの管理](../core/managing-schemas.md)