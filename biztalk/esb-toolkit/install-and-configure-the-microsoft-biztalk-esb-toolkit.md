---
title: インストールして、Microsoft BizTalk ESB Toolkit の構成 |Microsoft Docs
description: インストールして、BizTalk Server で ESB Toolkit を構成する手順の手順で指示
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
ms.openlocfilehash: 1672b3c2afd7dbca1f1843dedea81111a0a5a6a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400315"
---
# <a name="install-and-configure-the-microsoft-biztalk-esb-toolkit"></a>インストールして、Microsoft BizTalk ESB Toolkit の構成
以降では、BizTalk Server 2013 および新しいバージョンの[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]と統合されて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップします。 このトピックでは、インストールして構成する方法を示します[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、ESB Toolkit をアップグレードするコミュニティによって記述されたリンクも含まれています。  
  
> [!IMPORTANT]
>  BizTalk Server のインストールを開始する前にインストールする必要があります、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]します。  
  
## <a name="install"></a>インストール 
  
1. 実行、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.exe ファイルを管理者として。 セットアップでは、次のように選択します。**インストール[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** します。  
  
2. ライセンス条項に同意し、**次**します。  
  
3. **コンポーネントのインストール**をインストールして、選択するコンポーネントを選択して**次**します。  
  
4. **概要**、確認を選択して確認し、**インストール**します。  
  
5. 選択**完了**インストール ウィザードを終了します。  

インストール ログ ファイルが作成されます、' C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm' に似ています。 
  
## <a name="configure"></a>[構成] 
  
> [!IMPORTANT]
>  構成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成する前に[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]します。  
  
1. **開始**メニューの **Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** 、し、 **ESB 構成ツール**です。  
  
   > [!IMPORTANT]
   >  管理者として、ESB 構成ツールを実行します。  
  
2. 構成では、次のように選択します。**データベース サーバー**します。 ホストするデータベース サーバー名を入力、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]データベース。   
  
3. **IIS Web サービス**、ユーザー アカウントとパスワードを作成する IIS アプリケーションを実行している入力、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]します。 次に、アプリケーションをホストする IIS web サイトを入力します。  
  
4. **BizTalk ユーザー グループ**通常 ESB の構成に使用する既定のユーザー グループを一覧表示されます。  
  
   > [!IMPORTANT]
   >  この段階を選択できます**構成の適用**を構成する、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]これら既定の設定を使用します。 ただし、カスタム構成を実行する場合は、残りのステップを完了します。 次の手順で入力された値は、既定値よりも優先されます。  
  
5. 左側のウィンドウで展開**ESB の構成**、展開 * * 例外管理 * をクリックします。  
  
   -   例外管理データベースを構成しない場合を選択し、**データベース**、オフにし、**例外管理データベースを有効にする**します。
  
   -   新しいデータベースを作成する代わりに、既存のデータベースを使用しを選択する場合**データベース**を選択し、**既存のデータベースを使用して**します。 データベース サーバー名とデータベース名を入力します。  
  
   -   例外 web サービスを構成しない場合を選択し、**例外 Web サービス**、オフにし、**例外サービスを有効にする**します。  別の web サイトでこれらのサービスを実行する場合は、ここで入力することができます。  
  
6. 左側のウィンドウで展開**ESB コア コンポーネント**をクリックします。  
  
   -   行程データベースを構成しない場合を選択し、**行程データベース**、オフにし、**行程データベース**します。  
  
   -   既存の行程データベースを使用する場合を選択し、**行程データベース**を選択し、**既存のデータベースを使用して**します。 データベース サーバー名とデータベース名を入力します。  
  
   -   これらの web サービスを構成しない場合を選択し、**コア Web サービス**、オフにし、**コア サービスを有効にする**します。 別の web サイトでこれらのサービスを実行する場合は、ここで入力することができます。
  
7. 左側のウィンドウで次のように選択します。**構成**します。  
   インストールして構成する場合、 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] 、1 台のサーバー環境で次のように選択します。**ファイル構成ソース**します。 複数コンピューターの展開をセットアップする場合は、選択、 **SSO 構成ソース**、次を入力します。  
  
   -   **SSO サーバー**:SSO サーバーの名前を入力します。
  
   -   **構成ファイル**:省略記号を選択 **([...])**、し esb.config ファイル (\Program Files (x86) \Microsoft BizTalk ESB Toolkit) を参照
  
   -   **アプリケーション名**:SSO アプリケーションの名前を入力します。 たとえば、入力`ESB Toolkit`します。  
  
   -   **連絡先情報**:次の形式で有効な電子メール アドレス、適切な連絡先情報を入力します:`someone@example.com`します。  
  
   -   **管理者グループ名**:省略記号を選択 **([...])**、適切な管理グループを参照  
  
   -   **ユーザー グループ名**:省略記号を選択 **([...])**、適切なグループを参照  

8. 選択**構成の適用**します。 IIS を開き、アプリケーションに必要なことに注意してください。[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]を構成するときに指定した web サイトの下に作成されます。[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]します。  
  
9. **ESB 構成ツール**を選択します**ESB BizTalk アプリケーション**をクリックします。  
  
   - 選択**BizTalk Server で ESB コア コンポーネントを有効にする**でアプリケーションを作成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 選択**既定のバインドを使用して**このアプリケーションを既定のホストにバインドします。 選択**既定のバインドを使用しない**アプリケーションを既定のホストにバインドしたくない場合。 このシナリオでは、アプリケーションが作成されると、ホストにアプリケーションを明示的にバインドする必要があります。  
  
   - 選択**BizTalk Server で ESB JMS/WMQ コンポーネントを有効にする**でアプリケーションを作成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 選択**既定のバインドを使用して**このアプリケーションを既定のホストにバインドします。 選択**既定のバインドを使用しない**アプリケーションを既定のホストにバインドしたくない場合。 このシナリオでは、アプリケーションが作成されると、ホストにアプリケーションを明示的にバインドする必要があります。  
  
   - 選択**構成の適用**選択したアプリケーションを作成します。 アプリケーションが作成されていることを確認、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
## <a name="upgrade-esb-toolkit--community-addition"></a>ESB Toolkit – コミュニティからの追加をアップグレードします。  
 [インプレース ESB Toolkit 2.1 の 2.2 へのアップグレード](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)(http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)

## <a name="see-also"></a>関連項目
[インストールの問題、および一般的なエラー & 解像度をトラブルシューティングします。](troubleshooting-the-biztalk-esb-toolkit.md)