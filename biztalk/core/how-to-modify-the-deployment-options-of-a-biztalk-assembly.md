---
title: BizTalk アセンブリの展開オプションを変更する方法 |Microsoft Docs
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
ms.openlocfilehash: 16ba9dc20893a2899f7fbed78aefb3d1a0bcfdb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973587"
---
# <a name="how-to-modify-the-deployment-options-of-a-biztalk-assembly"></a>BizTalk アセンブリの展開オプションを変更する方法
このトピックでは、BizTalk Server 管理コンソールを使用して BizTalk アセンブリの展開オプションを変更する方法について説明します。  
  
 次の展開オプションを指定できます。  
  
-   **グローバル アセンブリ キャッシュへの追加に (gacutil) のリソースを追加します。** このオプションをオンにすると、アセンブリをアプリケーションに追加するとき、ローカル コンピューター上のグローバル アセンブリ キャッシュ (GAC) にアセンブリが追加されます。 さらに、後で、アセンブリを更新する場合 (右クリックし、をクリックして**更新**)、アセンブリが GAC に追加します。 アセンブリが現在 GAC に存在する場合は、このオプションのチェック ボックスをオフにしても、アセンブリが GAC から削除されることはありません。  
  
-   **MSI ファイルのインポート (gacutil) のグローバル アセンブリ キャッシュに追加します。** アプリケーションの .msi ファイルがインポートされるときに、ローカル コンピューターの GAC にアセンブリをインストールします。  
  
-   **MSI ファイル インストール (gacutil)、グローバル アセンブリ キャッシュに追加します。** アプリケーションが .msi ファイルからインストールされるときに、ローカル コンピューターの GAC にアセンブリをインストールします。  
  
-   **アップグレード先の場所:** パスをアプリケーションがインストールされているとき、アセンブリ ファイルにコピーされます。 パスを指定しないと、インストール時にローカル ファイル システムにアセンブリ ファイルがコピーされません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 また、アセンブリを直ちに GAC に追加するオプションを選択する場合は、アカウントはローカルの管理者グループのメンバーである必要もあります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-modify-the-deployment-options-of-a-biztalk-assembly"></a>BizTalk アセンブリの展開オプションを変更するには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで BizTalk Server 管理コンソールを展開し、展開オプションを変更する対象の BizTalk アセンブリが含まれる BizTalk グループを展開し、BizTalk アセンブリを格納しているアプリケーションを展開します。  
  
3. をクリックして、**リソース**フォルダーは、BizTalk アセンブリを右クリックし、順にクリックします**変更**します。  
  
4. **オプション**、必要な展開オプションのチェック ボックスを選択します。  
  
5. 必要に応じて、**先**アセンブリが、アプリケーションがインストールされているときにコピーされ、をクリックし、パスを編集する**OK**。  
  
## <a name="see-also"></a>参照  
 [BizTalk アセンブリの管理](../core/managing-biztalk-assemblies.md)