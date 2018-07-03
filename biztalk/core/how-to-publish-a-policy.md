---
title: ポリシーを公開する方法 |Microsoft Docs
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
ms.openlocfilehash: 0a4c272dfa76c8604224a9fc83ae888ce9b2c186
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996027"
---
# <a name="how-to-publish-a-policy"></a>ポリシーを公開する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk グループでポリシーを公開する方法について説明します。 公開したポリシーで使用できるように、BizTalk アプリケーションに追加する」の説明に従って[アプリケーションにポリシーを追加する方法](../core/how-to-add-a-policy-to-an-application.md)します。  
  
 ポリシーを公開するには、そのポリシーが BizTalk グループのルール エンジン データベースにあらかじめ存在している必要があります。 ルール エンジン データベースにポリシーをインポートするには、次の 3 つの方法があります。  
  
-   ポリシーを含むアプリケーションをインポートする方法。 この方法では、ポリシーはルール エンジン データベースに自動的にインポートされます。  
  
-   明示的にインポートできますポリシーをルール エンジン データベース、管理コンソールまたは BTSTask を使用して、」の説明に従って[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)します。  
  
-   追加できますポリシーをルール エンジン データベースに、ルール エンジン展開ウィザードを使用して」の説明に従って[とボキャブラリを展開およびポリシーの展開を解除する方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)します。  
  
> [!NOTE]
>  公開済みのポリシーはインポートした別のポリシーで上書きされる可能性がありますが、このオプションを指定すると、公開済みのボキャブラリは上書きされません。 公開済みのボキャブラリを更新するには、このボキャブラリをルール エンジン データベースから削除してから新しいバージョンをインポートする必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-publish-a-policy"></a>ポリシーを公開するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、公開、展開するポリシーが含まれる BizTalk グループ**アプリケーション**、順に展開**\<すべての成果物\>** します。  
  
3. クリックして**ポリシー**ポリシーを右クリックし、クリックして**発行**します。  
  
   > [!NOTE]
   >  ポリシーを公開するには、ポリシーが参照するすべてのアセンブリ必要がありますインストールのグローバル アセンブリ キャッシュ (GAC) に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を開く前にコンピューター **BizTalk Server 管理**します。 ときに**BizTalk Server 管理**が開かれるを GAC にインストールされているアセンブリのキャッシュを保持します。 このキャッシュはまで更新されません**BizTalk Server 管理**を閉じています。 ポリシーを公開しようとして、参照アセンブリが閉じる必要があります、GAC にインストールされていないために、パブリケーションが失敗した場合**BizTalk Server 管理**、GAC、オープンに参照アセンブリをインストール**BizTalk Server 管理**ポリシーを公開するとします。  
  
## <a name="see-also"></a>参照  
 [ポリシーの管理](../core/managing-policies.md)