---
title: 展開またはポリシーを展開解除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], undeploying
- deploying, policies
- policies, deploying
- managing [policies], deploying
- policies, undeploying
- undeploying, policies
ms.assetid: 9d26d4fe-9673-4baa-9927-02efda56b7a4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a5470c96bfb768528c255325681ce45a9af36c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338504"
---
# <a name="how-to-deploy-or-undeploy-a-policy"></a>展開またはポリシーを展開解除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、展開または手動でポリシーを展開解除する方法について説明します。 さらに、それに含まれるすべてのポリシーを展開するアプリケーションを自動的に起動し、そのポリシーを展開解除、アプリケーションを自動的に停止します。 ポリシーの展開に使用するアプリケーション内で有効に配置します。 ポリシーは、展開解除すると非アクティブとなり、BizTalk グループ内でそれを使用しているすべてのアプリケーションで動作しなくなります。  
  
 展開またはポリシーを展開解除、ときに、次の点に注意してくださいにしてください。  
  
-   ポリシーを展開するには、BizTalk グループのルール エンジン データベースに存在する必要があります。 ポリシーを含むアプリケーションをインポートすると、ポリシーが、ルール エンジン データベースに自動的にインポートまたは明示的にポリシーをインポートするルール エンジン データベースに、管理コンソールまたは BTSTask を使用して、 」の説明に従って[ポリシーをインポートする方法](../core/how-to-import-a-policy.md)します。 または、追加できますポリシーをルール エンジン データベースに、ルール エンジン展開ウィザードを使用して」の説明に従って[とボキャブラリを展開およびポリシーの展開を解除する方法](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)します。  
  
-   ポリシーを展開する前に発行して、」の説明に従って[ポリシーを公開する方法](../core/how-to-publish-a-policy.md)します。  
  
-   展開済みのポリシーを変更できません。 展開済みのポリシーを変更する場合は、最初に解除する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-deploy-or-undeploy-a-policy"></a>展開またはポリシーを展開解除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、展開または展開解除、および順に展開するポリシーが含まれる BizTalk グループを展開**\<すべての成果物\>**.  
  
3. クリックして**ポリシー**ポリシーを右クリックし、クリックして**デプロイ**または**Undeploy**します。  
  
## <a name="see-also"></a>参照  
 [ポリシーの管理](../core/managing-policies.md)   
 [BizTalk アプリケーション開始および停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)