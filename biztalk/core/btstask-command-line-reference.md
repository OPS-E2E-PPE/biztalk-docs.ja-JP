---
title: BTSTask コマンド ライン リファレンス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c350695-13e9-441a-9f1e-03cdc3e41328
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3df365e96c42865189a8e70aa5d1994a4b08a9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357797"
---
# <a name="btstask-command-line-reference"></a>BTSTask コマンド ライン リファレンス
このセクションの各トピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属する BTSTask コマンドライン ツールのリファレンス情報を紹介しています。 BTSTask を使用すると、さまざまなアプリケーション展開作業をコマンド ラインから実行できます。その例を次に示します。  
  
- BizTalk アプリケーションを AddApp コマンドで BizTalk 管理データベースに追加する。  
  
- AddResource コマンドでアプリケーションにアイテムを追加する。  
  
- アプリケーションとそのアイテムを ExportApp コマンドで .msi ファイルにエクスポートする。  
  
- バインド情報を ExportBindings コマンドで .xml ファイルにエクスポートする。  
  
- ImportApp コマンドを使用して、.msi ファイルからアプリケーションをインポートする。  
  
- ImportBindings コマンドを使用して、.xml ファイルからバインド情報をインポートする。  
  
- ListApp コマンドを使用して、アプリケーションに含まれるアイテムを、ローカル一意識別子 (LUID) と共に一覧表示する。  
  
- 特定の BizTalk グループを対象に、BizTalk 管理データベース内のすべてのアプリケーションを、ListApps コマンドを使用して一覧表示する。  
  
- ListPackage コマンドを使用して、.msi ファイル内のリソースを一覧表示する。  
  
- ListTypes コマンドを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がサポートしているアイテムの種類をすべて一覧表示する。  
  
- RemoveApp コマンドを使用して、BizTalk 管理データベースおよび BizTalk 管理コンソールからアプリケーションを削除する。  
  
- RemoveResource コマンドを使用して、アプリケーションからアイテムを削除する。  
  
- UninstallApp コマンドを使用して、アプリケーションをローカル コンピューターからアンインストールする。  
  
> [!IMPORTANT]
>  アプリケーションのインポート中に実行される処理前/処理後スクリプトで BTSTask コマンドを使用することはできません。 使用すると、インポートに失敗する場合があります。 スクリプトからは、インポート中に行われた変更を認識できないためです。  
  
 また、BTSTask の使用時に、コンソールの前景色を変更する方法を確認しておくことをお勧めします。 コンソールの背景色が白だと、BTSTask コンソールの出力が読みづらくなってしまうため、前景色の変更が必要になります。  
  
> [!NOTE]
>  スクリプトの実行が完了すると、成功の場合はゼロ (0) が、失敗の場合はゼロ以外の値が返されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [AddApp コマンド](../core/addapp-command.md)  
  
-   [AddResource コマンド](../core/addresource-command.md)  
  
-   [ExportApp コマンド](../core/exportapp-command.md)  
  
-   [ExportBindings コマンド](../core/exportbindings-command.md)  

- [ExportParties コマンド](../core/exportparties-command.md)

- [ExportSettings コマンド](../core/exportsettings-command.md)
  
-   [ImportApp コマンド](../core/importapp-command.md)  
  
-   [ImportBindings コマンド](../core/importbindings-command.md)  

- [ImportParties コマンド](../core/importparties-command.md)

- [ImportSettings コマンド](../core/importsettings-command.md)
  
-   [ListApp コマンド](../core/listapp-command.md)  
  
-   [ListApps コマンド](../core/listapps-command.md)  
  
-   [ListPackage コマンド](../core/listpackage-command.md)  
  
-   [ListTypes コマンド](../core/listtypes-command.md)  
  
-   [RemoveApp コマンド](../core/removeapp-command.md)  
  
-   [RemoveResource コマンド](../core/removeresource-command.md)  
  
-   [UninstallApp コマンド](../core/uninstallapp-command.md)  
  
-   [BTSTask のコンソールの色を編集する方法](../core/how-to-edit-the-console-colors-for-btstask.md)