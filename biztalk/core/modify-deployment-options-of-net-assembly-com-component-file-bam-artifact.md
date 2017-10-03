---
title: ".NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [.NET assemblies], deploying
- deploying, virtual directories
- managing [applications], deploying
- managing [applications], modifying
- definition files [BAM], modifying
- modifying, artifacts
- deploying, artifacts
- managing [certificates], deploying
- deploying, .NET assemblies
- COM components, deploying
- definition files [BAM], deploying
- virtual directories, deploying
- deploying, certificates
- modifying, deployment options
- virtual directories, modifying
- deploying, COM components
ms.assetid: 4955d420-d9ff-4d5a-82f4-fb16477a828c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6469f06b7b42ae1f8b45419fa0214682bd9fa67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-the-deployment-options-of-a-net-assembly-com-component-file-or-bam-artifact"></a>.NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更する方法
このトピックでは、BizTalk Server 管理コンソールを使用して次のリソース アイテムの展開オプションを変更する方法について説明します。  
  
-   .NET アセンブリ  
  
-   COM コンポーネント  
  
-   アドホック ファイル  
  
-   BAM アイテム  
  
 展開プロパティを変更して、アプリケーションをローカル コンピューターにインストールするときにアイテム ファイルがコピーされるコピー先の場所を変更できます。 パスを指定しない場合、ファイルはインストール時にローカル コンピューターにコピーされません。  
  
 また、.NET アセンブリの次のオプションを変更することもできます。  
  
-   **グローバル アセンブリ キャッシュに追加のリソース (gacutil) を追加します。** このオプションをオンにすると、アセンブリをアプリケーションに追加するとき、ローカル コンピューター上のグローバル アセンブリ キャッシュ (GAC) にアセンブリが追加されます。 また、後で、アセンブリを更新する場合 (右クリックし、をクリックして**更新**)、アセンブリが GAC に追加します。 アセンブリが現在 GAC に存在する場合は、このオプションのチェック ボックスをオフにしても、アセンブリが GAC から削除されることはありません。  
  
-   **MSI ファイル インポート (します gacutil) のグローバル アセンブリ キャッシュに追加します。** このオプションを選択すると、アプリケーションが .msi ファイルにエクスポートされ、.msi ファイルが BizTalk グループにインポートされた場合、アセンブリはインポート処理の一部として、ローカル コンピューターの GAC にインストールされます。  
  
-   **MSI ファイル インストール (します gacutil) のグローバル アセンブリ キャッシュに追加します。** このオプションを選択すると、アプリケーションが .msi ファイルにエクスポートされ、アプリケーションが .msi ファイルからコンピューターにインストールされた場合、アセンブリはインポート処理の一部として、ローカル コンピューターの GAC にインストールされます。  
  
-   **COM コンポーネント (regasm) に表示されるようにします。** このオプションをオンにすると、アプリケーションを .msi ファイルにエクスポートし、その .msi ファイルからアプリケーションをコンピューターにインストールした場合、マネージ COM アセンブリが、インストール処理の一部として、ローカル コンピューターの Windows レジストリに追加されます。 このオプションを指定する場合は、[エクスポート先] でファイルの場所も指定する必要があります。  
  
-   **登録サービスのコンポーネント (regsvcs)。** このオプションをオンにすると、アプリケーションを .msi ファイルにエクスポートし、その .msi ファイルからアプリケーションをコンピューターにインストールした場合、マネージ COM+ アセンブリが、インストール処理の一部として、ローカル コンピューターの Windows レジストリに追加されます。 このオプションを指定する場合は、[エクスポート先] でファイルの場所も指定する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 また、アセンブリを直ちに GAC に追加するオプションを選択する場合は、アカウントはローカルの管理者グループのメンバーである必要もあります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-modify-the-deployment-properties-of-a-resource-artifact"></a>リソース アイテムの展開プロパティを変更するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、展開オプションを変更するアイテムが含まれる BizTalk グループ、アイテムが含まれるアプリケーションの順に展開します。  
  
3.  クリックして、**リソース**フォルダーは、アイテムを右クリックし、をクリックして**変更**です。  
  
4.  **オプション** タブで、必要に応じて展開オプションを変更し、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)