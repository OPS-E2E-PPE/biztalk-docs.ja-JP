---
title: インストールして、Microsoft BizTalk ESB Toolkit の構成 |Microsoft ドキュメント
description: インストールして、BizTalk Server で ESB Toolkit を構成する手順の手順を実行して命令
caps.latest.revision: 8
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 698843f7-8361-4d02-9278-0e66f2a9f472
ms.author: mandia
ms.openlocfilehash: 33805fe58298e4f4729161a62742d3b204996b00
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22297002"
---
# <a name="install-and-configure-the-microsoft-biztalk-esb-toolkit"></a>インストールして、Microsoft BizTalk ESB Toolkit の構成
BizTalk Server 2013 と新しいバージョンでは、開始[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]と統合されて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップします。 このトピックは、インストールおよび構成する方法を示します[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、し、ESB Toolkit のアップグレードをコミュニティに書き込まれたリンクも含まれます。  
  
> [!IMPORTANT]
>  [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] のインストールを始める前に、BizTalk Server をインストールしておく必要があります。  
  
## <a name="install"></a>インストール 
  
1.  実行、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.exe ファイルを管理者として。 セットアップに、次のように選択します。**インストール[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** です。  
  
2.  ライセンス契約に同意し、**次**です。  
  
3.  **[コンポーネントのインストール]** で、インストールするコンポーネントを選択し、**[次へ]** を選択します。  
  
4.  **概要**、確認を選択して確認し、**インストール**です。  
  
5.  **[完了]** を選択して、インストール ウィザードを終了します。  

インストール ログ ファイルが作成、' C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm' に似ています。 
  
## <a name="configure"></a>[構成] 
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する前に、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] を構成する必要があります。  
  
1.  **開始**メニューの **Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** 、し、 **ESB 構成ツール**です。  
  
    > [!IMPORTANT]
    >  ESB 構成ツールを管理者として実行します。  
  
2.  構成では、次のように選択します。**データベース サーバー**です。 ホストするデータベース サーバー名を入力、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]データベース。   
  
3.  **IIS Web サービス**、ユーザー アカウントとによって作成された IIS アプリケーションを実行しているパスワードを入力、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]です。 次に、アプリケーションをホストする IIS web サイトを入力します。  
  
4.  **BizTalk ユーザー グループ**通常 ESB の構成に使用する既定のユーザー グループを一覧表示します。  
  
    > [!IMPORTANT]
    >  この段階を選択できます**構成の適用**を構成するのには[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]これらの既定の設定でします。 ただし、カスタム構成を実行する場合は、残りのステップを完了します。 次の手順で入力された値は、既定値よりも優先されます。  
  
5.  左側のウィンドウで展開**ESB 構成**、展開 * * 例外管理 * *、し。  
  
    -   例外管理データベースを構成しない場合を選択し、**データベース**、オフにし、**例外管理データベースを有効にする**です。
  
    -   新しいデータベースを作成する代わりに、既存のデータベースを使用しを選択する場合**データベース**を選択し、**既存のデータベースを使用して**です。 データベース サーバー名とデータベース名を入力します。  
  
    -   例外 web サービスを構成しない場合を選択し、**例外 Web サービス**、オフにし、**例外サービスを有効に**です。  別の web サイトの下でこれらのサービスを実行する場合は、ここで入力することができます。  
  
6.  左側のウィンドウで展開**ESB コア コンポーネント**、し。  
  
    -   行程データベースを構成しない場合を選択し、**行程データベース**、オフにし、**行程データベース**です。  
  
    -   既存行程データベースを使用する場合を選択し、**行程データベース**を選択して**既存のデータベースを使用して**です。 データベース サーバー名とデータベース名を入力します。  
  
    -   これらの web サービスを構成しない場合を選択し、**コア Web サービス**、オフにし、**コア サービスを有効に**です。 別の web サイトの下でこれらのサービスを実行する場合は、ここで入力することができます。
  
7.  左のペインで選択**構成**です。  
    インストールして構成する場合、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]単一サーバー環境で次のように選択します。**ファイル構成ソース**です。 複数コンピューターの展開を設定する場合は、選択、 **SSO 構成ソース**、次を入力します。  
  
    -   **SSO サーバー**: SSO サーバーの名前を入力してください
  
    -   **構成ファイル**: は、省略記号 **([...])**、し esb.config ファイル (\Program Files (x86) \Microsoft BizTalk ESB Toolkit) を参照
  
    -   **アプリケーション名**: SSO アプリケーションの名前を入力します。 たとえば、入力`ESB Toolkit`です。  
  
    -   **連絡先情報**: 次の形式で有効な電子メール アドレス、適切な連絡先情報を入力してください:`someone@example.com`です。  
  
    -   **管理者グループ名**: は、省略記号 **([...])**、適切な管理グループを参照  
  
    -   **ユーザー グループ名**: は、省略記号 **([...])**、適切なグループを参照  

8.  選択**構成を適用**です。 IIS を開き、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] に必要なアプリケーションが、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] の構成で指定した Web サイトに作成されていることを確認します。  
  
9. **ESB 構成ツール** **ESB BizTalk アプリケーション**、し。  
  
    -   選択**BizTalk Server で ESB コア コンポーネントを有効にする**でアプリケーションを作成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 選択**既定のバインドを使用**に既定のホストをこのアプリケーションをバインドします。 選択**既定のバインドを使用しないでください**アプリケーションを既定のホストにバインドしたくない場合。 このシナリオでは、アプリケーションを作成した後、ホストにアプリケーションを明示的に連結する必要があります。  
  
    -   選択**BizTalk Server で ESB JMS/WMQ コンポーネントを有効にする**でアプリケーションを作成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 選択**既定のバインドを使用**に既定のホストをこのアプリケーションをバインドします。 選択**既定のバインドを使用しないでください**アプリケーションを既定のホストにバインドしたくない場合。 このシナリオでは、アプリケーションを作成した後、ホストにアプリケーションを明示的に連結する必要があります。  
  
    -   選択**構成の適用**選択したアプリケーションを作成します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでアプリケーションが作成されたことを確認します。  
  
## <a name="upgrade-esb-toolkit--community-addition"></a>コミュニティによる補足 – ESB Toolkit のアップグレードします。  
 [インプレース アップグレード ESB Toolkit 2.1 2.2 に](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)(http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)

## <a name="see-also"></a>参照
[インストールの問題、一般的なエラーと解像度をトラブルシューティングします。](troubleshooting-the-biztalk-esb-toolkit.md)