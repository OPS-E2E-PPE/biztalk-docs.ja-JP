---
title: スキーマの追跡を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daef2bb1b118388897f98b6c2fa885b7fed4bbc0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000331"
---
# <a name="how-to-configure-tracking-for-a-schema"></a>スキーマの追跡を構成する方法
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、スキーマの追跡を構成する方法について説明します。 追跡を構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの [グループ ハブ] ページのクエリ ビューで、表示するメッセージのプロパティを指定します。  
  
 作成とクエリの使用に関する詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)します。 メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 追跡オプションを表示するだけの場合、BizTalk Server Operators グループのメンバーとしてログオンできます。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-tracking-for-a-schema"></a>スキーマの追跡を構成するには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**追跡を構成するスキーマが含まれる BizTalk グループを展開し、スキーマを含むアプリケーションを展開します。  
  
3. クリックして**スキーマ**、スキーマを右クリックし、クリックして**プロパティ**します。  
  
4. 左側のウィンドウで次のようにクリックします。**追跡**します。  
  
5. クリックして、メッセージを追跡するために使用するプロパティを指定するには、次のいずれかの**OK**:  
  
   -   選択、**すべてのメッセージ プロパティを選択します。** チェック ボックスを一覧表示されているすべてのプロパティを使用します。  
  
       > [!NOTE]
       >  このチェック ボックスは、昇格させたプロパティを含むスキーマに対してのみ選択できます。  
  
   -   使用する各プロパティのチェック ボックスをオンにします。  
  
       > [!NOTE]
       >  これは、昇格させたプロパティが含まれているスキーマでのみ使用できます。  
  
> [!NOTE]
>  メッセージの追跡によって、システムのパフォーマンスとストレージにオーバーヘッドが発生します。したがって、オプションは必要なもののみ選択してください。  
  
## <a name="see-also"></a>参照  
 [スキーマの管理](../core/managing-schemas.md)