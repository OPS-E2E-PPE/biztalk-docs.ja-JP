---
title: BizTalk アセンブリの展開オプションを変更する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, deploying
- managing [assemblies], modifying
- deploying, assemblies
- managing [assemblies], deploying
- assemblies, deploying
ms.assetid: d25e2f71-08bd-4786-ab6c-35ae4e88b8cc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58365383b1981ae40e87ee23891929bf05c8530e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007755"
---
# <a name="how-to-modify-the-deployment-options-of-a-biztalk-assembly"></a>BizTalk アセンブリの展開オプションを変更する方法
このトピックでは、BizTalk Server 管理コンソールを使用して BizTalk アセンブリの展開オプションを変更する方法について説明します。  
  
 次の展開オプションを指定できます。  
  
-   **グローバル アセンブリ キャッシュに追加のリソース (gacutil) を追加します。** このオプションをオンにすると、アセンブリをアプリケーションに追加するとき、ローカル コンピューター上のグローバル アセンブリ キャッシュ (GAC) にアセンブリが追加されます。 また、後で、アセンブリを更新する場合 (右クリックし、をクリックして**更新**)、アセンブリが GAC に追加します。 アセンブリが現在 GAC に存在する場合は、このオプションのチェック ボックスをオフにしても、アセンブリが GAC から削除されることはありません。  
  
-   **MSI ファイル インポート (します gacutil) のグローバル アセンブリ キャッシュに追加します。** アプリケーションの .msi ファイルがインポートされるときに、ローカル コンピューターの GAC にアセンブリをインストールします。  
  
-   **MSI ファイル インストール (します gacutil) のグローバル アセンブリ キャッシュに追加します。** アプリケーションが .msi ファイルからインストールされるときに、ローカル コンピューターの GAC にアセンブリをインストールします。  
  
-   **移行先の場所:** コピー先となるアセンブリ ファイルは、アプリケーションがインストールされているときにパスします。 パスを指定しないと、インストール時にローカル ファイル システムにアセンブリ ファイルがコピーされません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 また、アセンブリを直ちに GAC に追加するオプションを選択する場合は、アカウントはローカルの管理者グループのメンバーである必要もあります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-modify-the-deployment-options-of-a-biztalk-assembly"></a>BizTalk アセンブリの展開オプションを変更するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk Server 管理コンソールを展開し、展開オプションを変更する対象の BizTalk アセンブリが含まれる BizTalk グループを展開し、BizTalk アセンブリを含むアプリケーションの順に展開します。  
  
3.  クリックして、**リソース**フォルダーは、BizTalk アセンブリを右クリックし、をクリックして**変更**です。  
  
4.  **オプション**、必要な展開オプションのチェック ボックスをオンにします。  
  
5.  必要に応じて、**先の場所**アセンブリが、アプリケーションがインストールされているときにコピーされ、をクリックし、パスを編集**OK**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk アセンブリの管理](../core/managing-biztalk-assemblies.md)