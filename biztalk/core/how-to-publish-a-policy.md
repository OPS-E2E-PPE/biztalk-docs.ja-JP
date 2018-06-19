---
title: ポリシーを公開する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, publishing
- managing [policies], publishing
- publishing, policies
ms.assetid: 730c57a7-526f-40ca-8610-88216558e375
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d5e9604e950710911d4324d5b329173d184617b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971160"
---
# <a name="how-to-publish-a-policy"></a>ポリシーを公開する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk グループでポリシーを公開する方法について説明します。 公開したポリシーで使用できるように、BizTalk アプリケーションに追加する」の説明に従って[アプリケーションにポリシーを追加する方法](../core/how-to-add-a-policy-to-an-application.md)です。  
  
 ポリシーを公開するには、そのポリシーが BizTalk グループのルール エンジン データベースにあらかじめ存在している必要があります。 ルール エンジン データベースにポリシーをインポートするには、次の 3 つの方法があります。  
  
-   ポリシーを含むアプリケーションをインポートする方法。 この方法では、ポリシーはルール エンジン データベースに自動的にインポートされます。  
  
-   明示的にポリシーをインポートするルール エンジン データベースに、管理コンソールまたは BTSTask を使用して、」の説明に従って[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)です。  
  
-   追加できますポリシー ルール エンジン データベースにルール エンジン展開ウィザードを使用して」の説明に従って[展開と展開解除ポリシーとボキャブラリを方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)です。  
  
> [!NOTE]
>  公開済みのポリシーはインポートした別のポリシーで上書きされる可能性がありますが、このオプションを指定すると、公開済みのボキャブラリは上書きされません。 公開済みのボキャブラリを更新するには、このボキャブラリをルール エンジン データベースから削除してから新しいバージョンをインポートする必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-publish-a-policy"></a>ポリシーを公開するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、公開、展開するポリシーを含む BizTalk グループを展開して**アプリケーション**、順に展開**\<すべての成果物\>** です。  
  
3.  をクリックして**ポリシー**ポリシーを右クリックし、クリックして**発行**です。  
  
    > [!NOTE]
    >  ポリシーを公開するために、ポリシーによって参照されているすべてのアセンブリ必要がありますインストールのグローバル アセンブリ キャッシュ (GAC) に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を開く前にコンピューター **BizTalk Server 管理コンソール**です。 ときに**BizTalk Server 管理コンソール**が開くと、GAC にインストールされているアセンブリのキャッシュを保持します。 までこのキャッシュは更新されません**BizTalk Server 管理コンソール**が閉じられ、再び開きます。 ポリシーをパブリッシュしようとして、参照アセンブリが閉じる必要があります、GAC にインストールされていないために、パブリケーションが失敗した場合**BizTalk Server 管理コンソール**、開く、GAC に参照アセンブリをインストール**BizTalk Server 管理コンソール**、およびポリシーを公開します。  
  
## <a name="see-also"></a>参照  
 [ポリシーの管理](../core/managing-policies.md)