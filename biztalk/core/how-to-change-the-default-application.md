---
title: 既定のアプリケーションを変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, default
- applications, modifying
- modifying, applications
ms.assetid: cfa5e88f-0bbb-4edd-a840-722dcdcce266
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28c39f56d125044d234e2a073e6c27f52ad0afdf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342428"
---
# <a name="how-to-change-the-default-application"></a>既定のアプリケーションを変更する方法
このトピックでは、BizTalk Server 管理コンソールでアプリケーションのプロパティを編集することにより、既定のアプリケーションを変更する方法について説明します。 」の説明に従って、新しいアプリケーションを作成して、既定のアプリケーションとして指定することで、既定のアプリケーションに変更することもできます[アプリケーションを作成する方法](../core/how-to-create-an-application.md)します。  
  
 BizTalk Server をインストールすると、BizTalk Application 1 という名前の既定のアプリケーションが BizTalk 管理データベースに作成されて、BizTalk Server 管理コンソールに表示されます。 BizTalk Server を以前のバージョンからアップグレードすると、アイテムが自動的にこのアプリケーション内に置かれます。 また、BTSTask でアプリケーションを指定せずに Windows インストーラー (.msi) ファイルをインポートすると、.msi ファイルが既定のアプリケーションにインポートされます。  
  
 既定のアプリケーションは削除できませんが、どのアプリケーションを既定とするかは変更できます。 既定のアプリケーションを変更したら、必要に応じて、以前に既定であったアプリケーションを削除できます。 手順については、次を参照してください。 [BizTalk グループから BizTalk アプリケーションを削除する方法](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)します。  
  
 既定のアプリケーションを変更しても、アイテムはすべて、以前に既定であったアプリケーション内に残ります。 必要に応じて、アプリケーションからアイテムを明示的に移動できます。 手順については、次を参照してください。[を別のアプリケーション アイテムの移動方法](../core/how-to-move-an-artifact-to-a-different-application.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-change-the-default-application"></a>既定のアプリケーションを変更するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**を BizTalk グループを展開し、アプリケーションが既定の設定 をクリックするを右クリックして**プロパティ**します。  
  
3. 選択、 **、既定のアプリケーションをこのように**チェック ボックスをオンにして **[ok]** します。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)