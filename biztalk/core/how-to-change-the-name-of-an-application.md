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
ms.openlocfilehash: 0937e286e0416fbc4d56d155428872144034febc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342454"
---
# <a name="how-to-change-the-name-of-an-application"></a>アプリケーションの名前を変更する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、アプリケーションの名前を変更する方法を説明します。 使用するアプリケーション名は、グループに既に存在できません。  
  
> [!NOTE]
>  名前が変更されたアプリケーションへの参照を含むアプリケーションの .msi ファイルをエクスポートした場合、.msi ファイルをインポートするときに、参照が機能しなくなります。 新しいアプリケーション名で参照を更新する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-change-the-name-of-an-application"></a>アプリケーションの名前を変更するには  
  
1. クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、アプリケーションを変更して、をクリックする名前を右クリックして**プロパティ**します。  
  
3. **名前**ボックスで、アプリケーションの新しい名前を入力し、をクリックし、 **OK**。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)