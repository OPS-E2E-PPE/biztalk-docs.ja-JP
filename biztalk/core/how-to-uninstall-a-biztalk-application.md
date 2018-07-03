---
title: BizTalk アプリケーションをアンインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], uninstalling
- applications, uninstalling
- uninstalling, applications
- undeploying, uninstalling
ms.assetid: ab721c6e-194e-4b8a-bfd1-d0139d284373
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e18a657679c63f02d543a842615e459f732dc88a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010995"
---
# <a name="how-to-uninstall-a-biztalk-application"></a>BizTalk アプリケーションをアンインストールする方法
このトピックでは、コントロール パネルの [プログラムの追加と削除] または BTSTask コマンド ライン ツールを使用して、BizTalk アプリケーションをアンインストールする方法を説明します。 これらは、アプリケーションをアンインストールするためのサポートされているメソッドだけです。 BizTalk アプリケーションを更新したときなど、BizTalk 用の .msi ファイルが複数インストールされている場合、.msi ファイルをダブルクリックする方法や msiexec を使用する方法では BizTalk アプリケーションが完全にアンインストールされない可能性があります。したがって、これらのアンインストール方法はサポートされていません。  
  
> [!CAUTION]
>  実行中の BizTalk アプリケーションをアンインストールすると、アプリケーションでエラーが発生する場合があります。 この問題を回避するためが確認することをお勧めします。 ベスト プラクティスとしてはない実行中」の説明に従って、アプリケーションのインスタンスをサービス[すべてのサービス インスタンスを検索する方法](../core/how-to-search-for-all-service-instances.md)します。 かどうか、必要に応じてアプリケーションを停止できます、実行中のすべてのインスタンスを完全に停止する」の説明に従って完全停止 オプションを使用して、 [BizTalk アプリケーション開始および停止方法](../core/how-to-start-and-stop-a-biztalk-application.md)します。 この方法を実行すると、処理中のメッセージが完了しないことに注意してください。  
  
 BizTalk アプリケーションをアンインストールするときは、BizTalk に関連するすべてのファイルと設定が削除されるよう、処理前および処理後のスクリプトを BizTalk アプリケーションの .msi ファイルに追加する必要があります。 処理前または処理後のスクリプトを追加していない場合、このトピックの手順に従って BizTalk アプリケーションのファイルと設定をローカル ファイル システムから削除すると、次のような例外が生じます。  
  
- BizTalk アプリケーションに仮想ディレクトリが含まれている場合、BizTalk アプリケーションをインストールした後で仮想ディレクトリにファイルを追加していない限り、仮想ディレクトリとそのファイルは削除されます。 アプリケーションをインストールした後で仮想ディレクトリにファイルを追加した場合は、仮想ディレクトリも追加したファイルも削除されません。 仮想ディレクトリと追加ファイルを削除する場合は、明示的に削除する必要があります。  
  
- 処理前および処理後のスクリプトは削除されますが、インストール時またはアンインストール時にスクリプトによって追加されたファイルは削除されず、スクリプトによって実行されたアクションが取り消されることもありません。 スクリプトが追加したファイルを削除する場合、またはスクリプトのアクションを取り消す場合は、明示的に行う必要があります。  
  
  > [!NOTE]
  >  アプリケーションのインポート時に、展開プロパティでインポート先が指定されていた処理前または処理後のスクリプトだけが、アンインストール中に実行されます。 詳細については、次を参照してください。[より前に追加する方法または処理後のスクリプトをアプリケーションに](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)します。  
  
- BizTalk アプリケーションのアンインストール時に証明書は削除されません。 証明書を削除する場合は、明示的に行う必要があります。 また、コンポーネントは Windows レジストリから削除されず、BizTalk アセンブリはグローバル アセンブリ キャッシュ (GAC) から削除されません。 これらを削除する場合は、明示的に行う必要があります。 詳細については、次を参照してください。 [BizTalk アプリケーションの設定およびその他のファイルを削除する方法](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)します。  
  
  アンインストールの完了前にアンインストール操作を取り消すと、BizTalk Server はアンインストールをロールバックします。ただし、操作の取り消し前に処理前および処理後のスクリプトによって実行されたアクションはロールバックされません。 アンインストールを開始する前の状態にアプリケーションを復元するには、.msi ファイルをダブルクリックして、アプリケーションを再インストールしてください。 アプリケーションに対して複数の .msi ファイルがインストールされている場合、アプリケーションを再インストールするには、.msi ファイルが最初にインストールされた順序で各 .msi ファイルをダブルクリックする必要があります。  
  
  処理後のスクリプトの詳細については、次を参照してください。[アプリケーション展開のカスタマイズを前処理および後処理のスクリプトを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)します。  
  
> [!NOTE]
>  BizTalk アプリケーションを完全に展開解除する必要がありますも削除する、BizTalk グループから」の説明に従って[BizTalk グループから BizTalk アプリケーションを削除する方法](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、適切なアクセス許可でログオンする必要があります。 詳細については、次を参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="to-uninstall-a-biztalk-application"></a>BizTalk アプリケーションをアンインストールするには  
  
#### <a name="using-uninstall-or-change-a-program"></a>プログラムのアンインストールまたは変更を使用する場合  
  
1.  アプリケーションが実行されているコンピューターで、次のようにクリックします。**開始**、 をクリック**コントロール パネル**、し、ダブルクリック**プログラムと機能**します。  
  
2.  **[のアンインストールまたは変更するプログラム]** ページで、削除、およびをクリックし、BizTalk アプリケーションを右クリックして**アンインストール**します。  
  
     Windows インストーラーによって、指定したアプリケーションが削除されます。  
  
3.  複数のコンピューターでアプリケーションを実行している場合は、それぞれのコンピューターで上記の手順を繰り返します。  
  
#### <a name="using-the-command-line"></a>コマンドラインを使用  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask UninstallApp** [**/applicationname は:**<em>値</em>]  
  
    例:  
  
    **BTSTask UninstallApp applicationname:**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|アンインストールする BizTalk アプリケーションの名前。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md)   
 [UninstallApp コマンド](../core/uninstallapp-command.md)