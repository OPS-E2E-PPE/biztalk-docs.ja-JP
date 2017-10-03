---
title: "アプリケーションの名前を変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- naming conventions, renaming
- naming conventions, applications
- applications, renaming
ms.assetid: ae59c792-44bd-43e0-a4ae-e67bcad2e128
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4826688935bf18cd5288924d4544f484b3dcf0cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-name-of-an-application"></a>アプリケーションの名前を変更する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、アプリケーションの名前を変更する方法について説明します。 アプリケーションには、グループ内に既に存在するアプリケーション名を付けることはできません。  
  
> [!NOTE]
>  名前を変更したアプリケーションへの参照を持つアプリケーションの .msi ファイルをエクスポートした場合、その参照はその .msi ファイルをインポートしたときには機能しなくなります。 新しいアプリケーション名を使用して参照を更新する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-change-the-name-of-an-application"></a>アプリケーションの名前を変更するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、アプリケーションを変更して、をクリックする名前を右クリックして**プロパティ**です。  
  
3.  **名前**ボックスで、アプリケーションの新しい名前を入力し、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)