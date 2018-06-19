---
title: 既定のアプリケーションを変更する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 33b4ffb6fbbb2463b20a7d344d0f7f27811de23b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247986"
---
# <a name="how-to-change-the-default-application"></a>既定のアプリケーションを変更する方法
このトピックでは、BizTalk Server 管理コンソールでアプリケーションのプロパティを編集することにより、既定のアプリケーションを変更する方法について説明します。 」の説明に従って、新しいアプリケーションを作成して、既定のアプリケーションとして指定することで、既定のアプリケーションに変更することもできます[アプリケーションを作成する方法](../core/how-to-create-an-application.md)です。  
  
 BizTalk Server をインストールすると、BizTalk Application 1 という名前の既定のアプリケーションが BizTalk 管理データベースに作成されて、BizTalk Server 管理コンソールに表示されます。 BizTalk Server を以前のバージョンからアップグレードすると、アイテムが自動的にこのアプリケーション内に置かれます。 また、BTSTask でアプリケーションを指定せずに Windows インストーラー (.msi) ファイルをインポートすると、.msi ファイルが既定のアプリケーションにインポートされます。  
  
 既定のアプリケーションは削除できませんが、どのアプリケーションを既定とするかは変更できます。 既定のアプリケーションを変更したら、必要に応じて、以前に既定であったアプリケーションを削除できます。 手順については、次を参照してください。 [BizTalk グループから BizTalk アプリケーションを削除する方法](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)です。  
  
 既定のアプリケーションを変更しても、アイテムはすべて、以前に既定であったアプリケーション内に残ります。 必要に応じて、アプリケーションからアイテムを明示的に移動できます。 手順については、次を参照してください。[別のアプリケーションにアイテムを移動する方法](../core/how-to-move-an-artifact-to-a-different-application.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-change-the-default-application"></a>既定のアプリケーションを変更するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**を BizTalk グループを展開し、クリックして、既定にするアプリケーションを右クリックして**プロパティ**です。  
  
3.  選択、**しやすいように、既定のアプリケーション**チェック ボックスをオンし、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)