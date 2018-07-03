---
title: リソースを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [resources], refreshing
- refreshing resources
- resources, refreshing
ms.assetid: d6ff7c9d-8aaf-42a4-b1a3-00c05f6ac869
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 614cd1e2845994b5a0b009b56536f45a88f5bc2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986331"
---
# <a name="how-to-refresh-a-resource"></a>リソースを更新する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、リソース アイテムを更新する方法について説明します。 これにより、BizTalk 管理データベースのアイテム情報が更新されます。 これを行う別の方法は、BTSTask を使用してアプリケーションにアイテムを追加することで、 [AddResource コマンド](../core/addresource-command.md)上書きオプションを使用します。  
  
 リソース アイテムは、アプリケーションのリソース フォルダーに格納されています。 ソース ファイルに変更を加え、アプリケーションのファイルを更新したファイルで置き換える場合は、リソース アイテムを更新します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-refresh-a-resource-artifact"></a>リソース アイテムを更新するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、更新するリソース アイテムが含まれる BizTalk グループを展開し、成果物を含むアプリケーションを展開します。  
  
3. をクリックして、**リソース**フォルダー、ファイルを更新するには右クリックおよびクリック**変更**します。  
  
4. **リソースの変更** ダイアログ ボックスを更新するファイルを選択およびクリック**更新**します。  
  
5. 現在のファイルを置換する更新されたファイルに参照し、クリックして**OK**します。  
  
    現在のファイルが更新されたファイルに置き換えられます。 加算、構成に表示される設定で、**オプション**のタブ、**リソースの変更** ダイアログ ボックスが更新されたファイルに適用されます。 これらの設定を変更する方法についての詳細については、次のようにクリックします。**ヘルプ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプトを管理します。](../core/managing-pre-and-post-processing-scripts.md)   
 [.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [リソースの管理](../core/managing-resources.md)