---
title: 別のアプリケーションへの参照を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, referencing
ms.assetid: 6a177560-ee1f-403a-a68a-ade409a39a35
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6781ebc9c6cb0c3f7c68dfbbcff683193e15ac15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018553"
---
# <a name="how-to-add-a-reference-to-another-application"></a>他のアプリケーションへの参照を追加する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、1 つのアプリケーションから別のアプリケーションへの参照を追加する方法について説明します。 」の説明に従って、インポート ウィザードを使用して、アプリケーションをインポートするときに、その他のアプリケーションへの参照を追加することも[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。  
  
 同じ BizTalk グループの別のアプリケーション内に既に存在するアイテムを、現在のアプリケーションで使用する場合は、参照を追加します。 これは、ほとんどの種類のアイテムが BizTalk グループ内で一意である必要があるためです。 現在のアプリケーションに重複するアイテムを追加するのではなく、既にこのアイテムを含んでいる他のアプリケーションへの参照を追加します。 詳細については、[成果物をする必要がありますする内で一意で、アプリケーションまたはグループ](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)を参照してください。  
  
 仮想ディレクトリを使用する場合、または別のアプリケーションに既に存在する証明書を使用する場合は、参照を追加する必要はありません。 さらに、これらの場合は循環参照が作成される可能性があるため、参照を追加しないようにすることをお勧めします。  
  
 依存関係のあるアプリケーションをインポートする場合は、参照もインポートできます。 別のアプリケーションへの参照を追加すると、両方のアプリケーションの展開方法に影響することに注意してください。 詳細については、[依存関係とアプリケーションの展開](../core/dependencies-and-application-deployment.md)を参照してください。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-add-a-reference-to-another-application"></a>別のアプリケーションへの参照を追加するには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]] を展開し、参照を作成するアプリケーションを右クリックします。 これは、別のアプリケーションに含まれているアイテムを使用するアプリケーションです。  
  
3. をポイント**追加**し**参照**します。  
  
4. **アプリケーション**、(、または使用する複数のアイテムを格納しているアプリケーション) の参照を追加するアプリケーションの順にクリックします チェック ボックスをオンに**OK**します。  
  
    参照が現在のアプリケーションに追加されます。 コンソール ツリーで、このアプリケーションから参照したアプリケーションに、他の 1 つ以上のアプリケーションから参照されていることを示す手の形のアイコンが追加されます。  
  
    ![共有アプリケーション アイコン](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)