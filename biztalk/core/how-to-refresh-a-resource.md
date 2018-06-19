---
title: リソースを更新する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: bee05b9f137bbec92eccfa217084b66f1e5bf8ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254546"
---
# <a name="how-to-refresh-a-resource"></a>リソースを更新する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、リソース アイテムを更新する方法について説明します。 これにより、BizTalk 管理データベースのアイテム情報が更新されます。 これを行う別の方法は、BTSTask を使用してアプリケーションにアイテムを追加することによって、 [AddResource コマンド](../core/addresource-command.md)上書きオプションを使用します。  
  
 リソース アイテムは、アプリケーションのリソース フォルダーに格納されています。 ソース ファイルに変更を加え、アプリケーションのファイルを更新したファイルで置き換える場合は、リソース アイテムを更新します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-refresh-a-resource-artifact"></a>リソース アイテムを更新するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、更新するリソース アイテムが含まれる BizTalk グループを展開し、成果物を含むアプリケーションを展開します。  
  
3.  クリックして、**リソース**フォルダーを更新するファイルを右クリックしてをクリック**変更**です。  
  
4.  **リソースの変更**ダイアログ ボックスで更新するには、ファイルを選択してをクリック**更新**です。  
  
5.  現在のファイルを置換する更新されたファイルを参照し、をクリックして**OK**です。  
  
     現在のファイルが更新されたファイルに置き換えられます。 また、構成、設定の表示で、**オプション**のタブ、**リソースの変更** ダイアログ ボックスが更新されたファイルに適用されます。 これらの設定を変更する方法の詳細についてをクリックして**ヘルプ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプトを管理します。](../core/managing-pre-and-post-processing-scripts.md)   
 [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [リソースの管理](../core/managing-resources.md)