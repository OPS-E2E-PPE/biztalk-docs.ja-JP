---
title: アプリケーションの名前を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- naming conventions, renaming
- naming conventions, applications
- applications, renaming
ms.assetid: ae59c792-44bd-43e0-a4ae-e67bcad2e128
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5620bc481f5350e752b71a1706e187016ed25977
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992443"
---
# <a name="how-to-change-the-name-of-an-application"></a>アプリケーションの名前を変更する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、アプリケーションの名前を変更する方法について説明します。 アプリケーションには、グループ内に既に存在するアプリケーション名を付けることはできません。  
  
> [!NOTE]
>  名前を変更したアプリケーションへの参照を持つアプリケーションの .msi ファイルをエクスポートした場合、その参照はその .msi ファイルをインポートしたときには機能しなくなります。 新しいアプリケーション名を使用して参照を更新する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-change-the-name-of-an-application"></a>アプリケーションの名前を変更するには  
  
1. クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、アプリケーションを変更して、をクリックする名前を右クリックして**プロパティ**します。  
  
3. **名前**ボックスで、アプリケーションの新しい名前を入力し、をクリックし、 **OK**。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)